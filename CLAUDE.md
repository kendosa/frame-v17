# Publishing this folder

This folder is a ready-to-publish static website. To publish it on GitHub Pages:

1. Make sure the `gh` CLI is logged in (`gh auth status`; if not, run `gh auth login`).
2. From this folder:
   ```
   git init -b main
   git add .
   git commit -m "Frame V17 site"
   gh repo create frame-v17 --public --source=. --push
   gh api -X POST repos/{owner}/frame-v17/pages -f "source[branch]=main" -f "source[path]=/"
   ```
3. The site appears at `https://<username>.github.io/frame-v17/` within a minute or two.

Notes:
- Keep the repository public (GitHub Pages on free accounts requires public repos).
- No build step; `.nojekyll` is included so files are served as-is.
- Total size is about 5 MB, far under GitHub's limits.
