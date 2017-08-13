# `thinkings`

A blog originally in denial of its identity. I almost named it `muse`. Created 17 July 2017.

For every commit to this repository, GitHub Pages will run Jekyll to rebuild the pages in the site, from the content in the Markdown files.

## Gotchas
- use `{{site.github.url}}` before any internal url to get the correct prefix
- "Page build failed" (found in Repository Settings --> GitHub Pages)
  - when using `{% post_url ... %}`, check that the post you want to link to definitely exists (but `{% link ... %}` is fine)

## Local preview with Jekyll

### Initial setup
These instructions are based on https://help.github.com/articles/setting-up-your-github-pages-site-locally-with-jekyll/. Worked for me on 2017-07-17 with Ubuntu 16.04 64-bit, except I needed `sudo` for installing anything with `gem`.
1. Confirm you have ruby: `ruby --version`. If you don't, install Ruby: `sudo apt-get install ruby-full`. It prompted me to install `ffi` separately, so I did. 
2. Install bundler: `gem install bundler`.
3. Clone this git repository to your machine.
3. In the clone destination (e.g. `~/Programming/thinkings`), save these lines to a file called "Gemfile":
    ```
    source 'https://rubygems.org'
    gem 'github-pages', group: :jekyll_plugins
    ```
4. Install dependencies: `bundler install`.

### Local server
1. Update dependencies: `bundler update`.
2. Run server (with option to render `_drafts`): `bundle exec jekyll serve --drafts`
3. Navigate to http://localhost:4000 to preview the site.
Changes to files _should_ trigger automatic regeneration of pages. Sometimes I have to terminate and restart the server to force regeneration.

### Writing a draft
1. Add a new file in the `_drafts` directory. It doesn't need the date in its filename.
2. When you run the server with `--drafts`, the draft will be treated like a normal page.
3. Publish the draft by moving the file to the appropriate directory (e.g. `_posts`) and renaming it to include the date if needed.
See [Jekyll: Working with drafts](https://jekyllrb.com/docs/drafts/) for more information.

## Resources
- [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/)
- [GitHub Pages documentation](https://help.github.com/categories/github-pages-basics/)
- [Jekyll documentation](https://jekyllrb.com/docs/home/)
- [Emoji cheatsheet](https://www.webpagefx.com/tools/emoji-cheat-sheet/)
