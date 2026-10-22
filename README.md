# iamibrahimbello.xyz

Ibrahim Bello's portfolio. One static page (`index.html`, no build step), hosted on GitHub Pages.

## Edit
- **Projects** (the hero carousel): the `PROJECTS` list near the top of the `<script>` in `index.html`.
- **About text, links, email**: search `index.html` for `todo` (dashed gold boxes on the page) and replace them.
- **Images / video**: `assets/`. Keep files small (under ~5 MB); put long films on YouTube and link them.

## Preview locally
    python3 -m http.server 4173      # then open http://localhost:4173

## Deploy (GitHub Pages)
1. Create a public repo on GitHub (e.g. `iamibrahimbello`) and push this folder to `main`.
2. Repo → Settings → Pages → Source: "Deploy from a branch", branch `main`, folder `/ (root)`.
3. Custom domain: buy `iamibrahimbello.xyz`, enter it under Settings → Pages → Custom domain (this writes
   a `CNAME` file), then at your registrar add the DNS records GitHub shows (A records for the apex
   domain, a CNAME for `www`). Tick "Enforce HTTPS" once it's available.

Design inspired by carterogunsola.com; all code here is original.
