# raymondww.github.io

Personal site built with [Quarto](https://quarto.org) — a minimalist, dark homepage plus a blog
where every post is a `.qmd` file.

## Setup (one-time)

1. Install Quarto: `brew install --cask quarto` (or download from quarto.org).
2. Preview locally: `quarto preview` — opens the site at `http://localhost:4000` and live-reloads
   as you edit.

## Writing a new blog post

1. Copy `blog/posts/welcome-to-the-blog/` to a new folder, e.g. `blog/posts/my-new-post/`.
2. Edit `index.qmd` inside it — update the `title`, `description`, `date`, and `categories` in the
   front matter, then write the post body in Markdown (code, images, and plots all work).
3. Commit and push. The GitHub Action (`.github/workflows/publish.yml`) renders the site and
   publishes it to the `gh-pages` branch automatically.

## Editing the homepage

Homepage content lives in `index.qmd`. Layout and colors live in `styles.scss` (the dark palette is
defined at the top under `:root`).

## GitHub Pages setup (one-time, on GitHub.com)

1. Push this repo to GitHub (`git push`).
2. Go to **Settings → Pages**.
3. Under **Build and deployment → Source**, choose **Deploy from a branch**.
4. Set the branch to **gh-pages** / **/(root)**, then Save.
5. The first push to `main` will trigger the Action, create the `gh-pages` branch, and publish the
   site. After that, every push to `main` auto-publishes.

## Notes

- `docs/` is the local Quarto build output — it's gitignored; you never commit it, the Action builds
  it in CI.
- The old single-file `index.html` has been moved to `_to_delete/` — once you've confirmed the new
  site looks right, delete that folder and remove it from git with `git rm -r _to_delete`.
