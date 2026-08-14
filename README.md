# lve.com

My personal site.

**Live:** https://luke-edward.github.io/LVE-COM/

Static single page — no build step. `index.html` plus `assets/`. GitHub Pages
serves it from `main` at the repo root.

## Local preview

```sh
python3 -m http.server 8000
# then open http://127.0.0.1:8000/
```

## Notes

- Every asset path is relative, so the site works from a project subpath, a
  domain root, or a custom domain without changes.
- Asset filenames are all lowercase. Pages serves from a case-sensitive
  filesystem while macOS is case-insensitive, so a casing mismatch will work
  locally and 404 in production — check the deployed URL, not just localhost.
- The works grid must keep `id="projects"`. `assets/js/master-dist.js` looks it
  up by that id to build the WebGL grid-to-fullscreen effect.
- Thumbnails in the works grid and `.item-full` panels in the lightbox are
  matched **by index**. Adding one without the other silently opens the wrong
  panel, so keep the two lists the same length and in the same order.
- Credit: the design is based on work by
  [Patrick David](https://www.patrickdavid.net/).
