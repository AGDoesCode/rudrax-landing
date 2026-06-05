# Rudrax.AI Landing Page

Static landing site for [rudrax.ai](https://rudrax.ai) — the umbrella company for micro SaaS, Android, iOS, and Windows apps.

## Local development

```bash
npm install
npm run dev
```

Open [http://localhost:4321](http://localhost:4321).

## Build

```bash
npm run build
```

Output is in `dist/`.

## Deploy free on Cloudflare Pages

1. Push this folder to a GitHub repo.
2. In [Cloudflare Dashboard](https://dash.cloudflare.com) → **Workers & Pages** → **Create** → **Pages** → **Connect to Git**.
3. Select the repo and use these settings:
   - **Framework preset:** Astro
   - **Build command:** `npm run build`
   - **Build output directory:** `dist`
4. Deploy. You'll get a URL like `rudrax-landing.pages.dev`.
5. In Pages → **Custom domains**, add `rudrax.ai` and `www.rudrax.ai`.

## DNS (SquareSpace)

In **SquareSpace → Domains → rudrax.ai → DNS**, add what Cloudflare Pages shows you. Typically:

| Type  | Host | Value                    |
|-------|------|--------------------------|
| CNAME | www  | `your-project.pages.dev` |

For the root domain (`@`), either:

- Move DNS to Cloudflare (free, recommended), or
- Use SquareSpace forwarding: `@` → `https://www.rudrax.ai`

SSL is automatic once DNS propagates (usually 5–30 minutes).

## Alternative: Vercel

Import the GitHub repo at [vercel.com](https://vercel.com). Vercel auto-detects Astro. Add `rudrax.ai` as a custom domain and set DNS:

| Type  | Host | Value                 |
|-------|------|-----------------------|
| A     | @    | `76.76.21.21`         |
| CNAME | www  | `cname.vercel-dns.com`|

## Contact email

The site uses `hello@rudrax.ai`. Set up that mailbox or alias in your email provider, or change the address in `src/pages/index.astro`.
