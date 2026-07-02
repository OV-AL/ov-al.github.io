# ov-al.github.io

Public GitHub Pages host for the **Oval** documentation site — served at
<https://ov-al.github.io>.

> **Do not edit this repository by hand.**

The site is authored and built in the private **`OV-AL/oval`** repo (under `site/`,
an Astro Starlight project). Its `site-deploy` GitHub Actions workflow builds the
static output and force-pushes it to the **`gh-pages`** branch here, which GitHub
Pages serves. The `main` branch holds only this notice.

## How it works

```
OV-AL/oval (private)                      OV-AL/ov-al.github.io (this repo, public)
  site/            --- pnpm build --->      gh-pages branch  --- GitHub Pages --->  https://ov-al.github.io
  .github/workflows/site-deploy.yml
```

Publishing uses an SSH deploy key with write access, scoped to this repository. The
private half lives as the `ACTIONS_DEPLOY_KEY` secret in `OV-AL/oval`.

To change the docs, edit `site/` in `OV-AL/oval` and push to `main` there.
