---
title: Home
---

# Static Content Example

This site is generated from plain Markdown files in the
[repository](https://github.com/velvet-bunny/static-content-example) and published with GitHub Pages.

{% include search.html %}

Each section lives in its own folder and gets its own styling:

- [Micro-guides]({{ '/micro-guides/' | relative_url }}) — short, to-the-point guides.
- [Idle-guides]({{ '/idle-guides/' | relative_url }}) — longer reads for a slow afternoon.
- [Cyberpunk-guides]({{ '/cyberpunk-guides/' | relative_url }}) — same Markdown, very different look.

## How this site is made

- **Content:** every page is a plain Markdown (`.md`) file stored in a [GitHub repository](https://github.com/velvet-bunny/static-content-example).
- **Sections:** each section is simply a folder, such as `micro-guides/` or `cyberpunk-guides/`.
- **Adding a page:** drop a new Markdown file into a folder with a title at the top, and it appears in that section's list.
- **Look and feel:** one shared page template plus a separate stylesheet per section gives each section its own style.
- **From Markdown to web pages:** [Jekyll](https://jekyllrb.com/), a free tool built into GitHub Pages, converts the Markdown files into web pages.
- **Publishing:** whenever a change is saved (pushed) to the repository, an automated GitHub Actions workflow rebuilds and publishes the site in about a minute.
- **Hosting:** [GitHub Pages](https://pages.github.com/) hosts the site for free[^free] at a `github.io` address[^domain].
- **Search:** [Pagefind](https://pagefind.app/) builds a search index while publishing, and the search box runs entirely in your browser.
- **Nothing to maintain:** there are no servers or databases, just static web pages.
- **Static doesn't mean limited:** "static" only means the pages are prepared in advance, so interactive features like the search box above still work because they run in your browser.
- **Moving on from GitHub Pages?** Jekyll is free and open source, so the same Markdown files and templates can be built and hosted almost anywhere else.

[^free]: Free as long as the repository is public. To keep the Markdown files private, you need a paid GitHub plan: Pro for a personal account (about $4/month) or Team for an organization (about $4 per user/month); see [GitHub pricing](https://github.com/pricing). The website itself is still public either way.
[^domain]: You can also use your own domain name, such as `guides.example.com`, instead of the `github.io` address; see [GitHub's guide to custom domains](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site).
