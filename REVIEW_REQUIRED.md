# Review required before publication

This is a working checklist, not a statement that the site or app is compliant.
Confirm each item with the relevant Bytewise owner and, where appropriate, legal
counsel before publishing the policy or submitting an App Review.

- [ ] Confirm Bytewise's legal entity name, business address, jurisdiction, and
  the identity of the privacy-policy controller/operator.
- [ ] Confirm that `bytewiserpersona@yahoo.com` is Bytewise's approved,
  monitored privacy and deletion-request address.
- [ ] Confirm the Meta Developer App's display name, app ID, owner, connected
  account types, intended production status, and supported Meta products.
- [ ] Verify the exact Meta permissions, feature access, endpoint(s), fields,
  account types, and review status required for the proposed Threads searches.
  Do not assume a platform-wide trending-topics endpoint exists.
- [ ] Verify whether authorized keyword search supports the intended `TOP`
  and/or `RECENT` result modes for the app, account, and use case, and confirm
  all applicable rate limits and data-use restrictions.
- [ ] Confirm which public Threads fields are actually requested and needed
  (post text, post ID/URL, username, timestamp, and any engagement metadata),
  and whether any connected-account data is also accessed.
- [ ] Confirm that Threads discovery remains in development/testing and specify
  exactly what is deployed, enabled, and demonstrable. Current workflow notes
  report missing Threads-search permission in a separate research workflow.
- [ ] Identify every AI provider that can receive Meta-derived information,
  including whether QwenCloud is selected or only under consideration. Confirm
  the exact payload, purpose, provider region/subprocessors, retention and
  training terms, contractual controls, and compatibility with Meta's terms.
- [ ] Confirm whether existing OpenAI or other content-generation/QA steps
  receive any Threads-derived information. Provider integrations in workflow
  files do not by themselves establish which production executions send which
  data.
- [ ] Inspect n8n execution-history settings, successful/error/manual execution
  retention, access, and deletion behavior for every relevant workflow. Some
  workflow documentation indicates execution data may be saved; no retention
  period is established by this draft.
- [ ] Confirm the Supabase data categories, including persona information,
  approved topics, generated content, queue records, publishing statuses, and
  related operational data; verify retention, backups, access, and deletion
  behavior. Confirm raw Threads search results are not persistently stored
  there as intended.
- [ ] Verify how Meta access tokens and other API credentials are stored,
  scoped, accessed, rotated, and removed. Confirm the wording in the policy
  against the actual n8n and provider configurations.
- [ ] Confirm the incident/security practices Bytewise can accurately
  describe, without implying unverified encryption or other guarantees.
- [ ] Confirm applicable privacy rights, request identity checks, exceptions,
  response process, cross-provider deletion steps, and any lawful retention.
  No response deadline or deletion timeline is promised in the draft.
- [ ] Confirm the exact Meta UI instructions for revoking the app's access;
  settings labels and navigation can vary by account and product.
- [ ] Before launch, test the deployed site's direct `/`, `/privacy`, and
  `/data-deletion` routes; confirm HTTPS, public access, no authentication or
  geographic blocks, and no `noindex` or restrictive `robots.txt` rule.
- [ ] Set the effective publication date after review and verify the final
  public URLs and contact address.
