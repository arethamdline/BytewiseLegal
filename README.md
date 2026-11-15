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

## Vercel setup

Import the `bytewise-meta-legal` repository into the authorized Vercel account,
set the project Root Directory to `site`, choose the **Other** framework preset,
and leave the build command empty. The site consists of plain HTML and CSS.
Configure a custom domain only after legal review and approval of every item in
[`REVIEW_REQUIRED.md`](./REVIEW_REQUIRED.md).

Do not publish this draft until the unresolved factual, operational, and legal
statements have been reviewed. `META_APP_REVIEW.md` and `REVIEW_REQUIRED.md`
belong to the repository, outside the Vercel site root.
