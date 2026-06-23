# Curie Website Redesign — Prototype

An interactive HTML prototype of the revamped **Curie.md** website, built from a Claude design composition. It is a single self-contained demo (Home, Briefs, Games, AI Tools pages with working in-page navigation) used to preview the redesign direction and share it with the team.

**Live demo:** https://shriram-bharadwaj-zoomrx.github.io/curie-website-revamp/

## Contents

| File | Purpose |
|------|---------|
| `index.html` | The prototype (Design Composer template + React runtime via CDN) |
| `support.js` | Design Composer runtime that renders the prototype |
| `curie-website-revamp-spec.md` | Redesign spec / reference document |

## Running locally

Serve over HTTP (the runtime fetches the page itself, so `file://` won't work):

```bash
python3 -m http.server 8000
# open http://localhost:8000
```

> Prototype only — not production code.
