# lve.com

My personal site.

**Live:** https://luke-edward.github.io/LVE-COM/

One self-contained HTML file, about 16 KB. No JavaScript, no build step, no
external requests, no webfonts — it renders instantly and can't break from a
failed script. GitHub Pages serves it from `main` at the repo root.

## Local preview

```sh
python3 -m http.server 8000
# then open http://127.0.0.1:8000/
```

## Editing

The page is generated, so don't hand-edit `index.html` — the next build would
overwrite it. Content lives in `content.py` and the layout in `build_v1.py`
(kept in the session workspace, not this repo). To change copy:

```sh
python3 build_v1.py --root > index.html
```

Without `--root` it emits the preview variant, which uses `../` asset paths and
is marked `noindex`.

## Notes

- Asset filenames are lowercase on purpose. Pages serves from a case-sensitive
  filesystem while macOS is case-insensitive, so a casing mismatch works
  locally and 404s in production. Check the deployed URL, not just localhost.
- Colors respond to `prefers-color-scheme`; motion respects
  `prefers-reduced-motion`.
- The previous design was a third-party template (credit: Patrick David) and
  was replaced in full. It's still in git history if it's ever needed —
  see commit `a0e874a`.
