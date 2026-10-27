# Static Blog

This is my personal blog / portfolio. It was created with [Static](https://static.devdojo.com)
and now builds with [Statico](https://github.com/adrianodias8/statico), a single-binary
static site generator that began as a Rust rewrite of Static. The site files are unchanged —
same `pages/`, `layouts/`, `includes/`, `collections/` and `content/`.

![Cover Photo](assets/images/cover.jpg)



Install Statico: there is no Node.js to install, just one binary. Open your terminal and run:

`curl -fsSL https://raw.githubusercontent.com/adrianodias8/statico/main/packaging/install.sh | sh`

This puts a `statico` binary in `~/.local/bin`. Builds for other platforms are on the
[releases page](https://github.com/adrianodias8/statico/releases).

Get the Project: clone this repository and move into it:

`git clone https://github.com/adrianodias8/static-blog.git && cd static-blog`

Start the Development Server: launch the local development server with:

`statico dev`

Your site is now running locally at http://localhost:3000/, and it reloads when you save a
file. Open this URL in your browser to view your site.

Check Before Pushing: build the site and verify it with:

`statico check`

This reports broken links, missing `#anchor` targets, images without alt text and unresolved
placeholders. Zero errors means it is ready.



Pushing to `main` builds the site and publishes it to GitHub Pages — see
[.github/workflows/static.yml](.github/workflows/static.yml). The custom domain follows
https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site

Go live!
