# deadc0de.sh

Personal security blog, built with [Hugo](https://gohugo.io) and the
**phosphor** theme.

## Local development

```bash
git clone --recurse-submodules git@github.com:anaskalt/deadc0de.sh.git
cd deadc0de.sh
hugo server -D            # http://localhost:1313
```

If you forgot `--recurse-submodules`:

```bash
git submodule update --init --recursive
```

## Add the theme (first time only)

```bash
git submodule add https://github.com/anaskalt/phosphor themes/phosphor
git submodule update --init --recursive
```

## Write a post

```bash
hugo new content posts/my-writeup.md
# set draft = false when ready
```

## Deploy

Pushing to `main` builds and deploys to GitHub Pages automatically
(`.github/workflows/deploy.yml`). The custom domain is set via `static/CNAME`.

## Update the theme later

```bash
git -C themes/phosphor fetch --tags
git -C themes/phosphor checkout v0.2.0     # or: pull origin main
git add themes/phosphor && git commit -m "chore: bump phosphor theme"
```
