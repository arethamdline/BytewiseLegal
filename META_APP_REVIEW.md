# Bytewise Meta Developer App — App Review Notes

## Purpose and identity

The Bytewise Meta Developer App is an API integration for Bytewise's internal
n8n-based content automation system. It is not a consumer-facing mobile or web
application. Bytewise uses the integration to connect authorized social
accounts to internal research, content review, scheduling, and publishing
workflows.

## Why Threads discovery is being developed

Bytewise is developing and testing a Threads Trend Discovery feature. The goal
is to identify relevant public discussions and emerging conversations that may
inform original content for individual social personas. This is not a claim
that a platform-wide trending feed is available. The planned method is
authorized Meta API access, including official keyword search with `TOP` or
`RECENT` results only where Meta supports it for the app and approved use case.
Bytewise will not scrape Threads or bypass authentication, access controls, or
rate limits.

The project workspace contains a development workflow path that constructs
keyword queries and requests `TOP` results. A separate social-research workflow
reports Threads public search unavailable because the required Meta permission
is missing. Therefore, the feature must be described as in development/testing,
not as an operational or approved production capability. Confirm the current
app and workflow state before the review demonstration.

## Data requested or processed

If permitted by Meta and enabled for the app, the discovery flow may process
only public Threads results relevant to selected keyword queries:

- public post text and discussion/topic context;
- post identifiers and URLs;
- public usernames or creator information when necessary;
- publication timestamps; and
- public engagement metadata only where available and authorized.

The API request and actual returned fields must be verified against the
permissions and API version presented for review. The workflow implementation
currently shown in project files extracts post IDs, text, usernames, permalinks,
and timestamps; this is not evidence that access is currently granted or that
all fields will be used in production.

## Processing and storage

The intended path is:

1. Make an authorized Meta API keyword-search request from an n8n workflow.
2. Filter and summarize relevant returned public discussions for persona
   relevance, without treating social discussion as proof that a claim is true.
3. Pass selected topic information through internal research and verification
   steps; verify factual claims against reliable sources.
4. Generate original content with AI writing workflows, apply quality checks,
   and route approved items to existing scheduling and publishing workflows.

Raw Threads trend-search results are not intended to be permanently stored in
Supabase. They may be processed temporarily in n8n. However, n8n execution
history may retain workflow inputs and outputs, depending on workflow
configuration and execution-history retention settings. Those settings and
retention periods must be confirmed before submission.

The broader automation system may store persona information, approved topics,
generated content, content-queue records, publishing statuses, and related
operational data in Supabase. These persistent operational records are distinct
from the raw Threads search results.

## AI provider processing

The planned trend-analysis flow may send the minimum necessary selected
information to an external AI provider for analysis. QwenCloud is an example
under consideration, not a confirmed provider for this feature. Existing
workflow files also show AI provider integrations in content-generation and
quality-review steps, but that alone does not establish whether Threads-derived
data reaches those providers.

Before App Review, Bytewise must identify the exact provider(s), data fields,
purpose, region, subprocessors, retention and training terms, and applicable
contractual controls. Confirm that each transfer and subsequent use is allowed
by Meta's terms and applicable privacy requirements. Do not claim provider
guarantees unless verified.

## Permissions and capabilities to verify

Do not infer or invent permission names. Before submitting, use the current
Meta developer documentation and App Dashboard to verify:

- the exact Threads API permission(s) and feature access for public keyword
  search and the intended result modes;
- any separate permissions required to read connected-account information or
  publish content;
- the exact fields and account types each permission enables;
- review, testing, rate-limit, and data-use requirements; and
- whether access is development-only, approved for production, or unavailable.

Only request access needed for the demonstrated functionality. This document
does not claim that Meta has approved any permission or access.

## Features not yet represented as deployed

- Threads Trend Discovery is being developed and tested; current project
  documentation reports a missing search permission in a separate research
  workflow.
- No unrestricted official trending-topics endpoint is assumed.
- AI-based trend analysis with QwenCloud is not confirmed as deployed.
- No automated data-deletion callback is implemented; deletion requests are
  intended to be handled by email and manual review.

Other automation workflows for content generation, quality review, scheduling,
and publishing exist in the project workspace. Confirm which are enabled and
in scope before describing them as operational in App Review.

## Suggested reviewer demonstration

Use a test account and a review-safe, authorized configuration. Show:

1. The app identity and the internal n8n workflow that uses it.
2. The exact permission-gated official API request, keyword and supported
   result mode, with credentials redacted.
3. The access-denied or no-results behavior if Meta access is not available;
   do not present simulated results as live API data.
4. A redacted example of the minimum returned fields and how relevance is
   assessed.
5. Any external AI handoff using a clearly identified provider and redacted,
   minimal sample payload, or state that the integration is not yet enabled.
6. Topic verification, content quality review, and the approval step before a
   topic is saved or content is scheduled.
7. Where persistent operational records are held and how execution history is
   configured, without exposing secrets or unrelated user data.
8. The manual email-based data deletion instructions and how a user revokes
   Meta permissions.

## Submission caveat

This is an implementation-oriented explanation, not legal advice or a claim of
Meta approval or policy compliance. Reconcile it with the current app
configuration, actual API responses, provider contracts, data-retention
settings, and Meta's current terms before submission.
