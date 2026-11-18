# Bytewise Meta Legal

A lightweight static legal-information site for the Bytewise Meta Developer App.
This project is separate from the n8n workflow workspace and has no runtime
dependencies, analytics, tracking cookies, user accounts, or database.

## Local preview

Serve the `site` directory with any static file server. For example:

```sh
cd site
python3 -m http.server 8000
```

Open `http://localhost:8000/`, `/privacy`, and `/data-deletion`.

## Netlify setup

Import the `arethamdline/BytewiseLegal` repository into Netlify. The
[`netlify.toml`](./netlify.toml) configuration sets `site` as the publish
directory; no build command or dependencies are needed. If configuring the
project in the Netlify UI, leave the base directory and build command empty and
set the publish directory to `site`.

The public pages are `/`, `/privacy/`, and `/data-deletion/`. Configure a custom
domain only after legal review and approval of every item in
[`REVIEW_REQUIRED.md`](./REVIEW_REQUIRED.md).

Do not publish this draft until the unresolved factual, operational, and legal
statements have been reviewed. `META_APP_REVIEW.md` and `REVIEW_REQUIRED.md`
belong to the repository, outside the Vercel site root.
