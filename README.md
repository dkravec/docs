# GymTracker Documentation Site

Built with [Jekyll](https://jekyllrb.com) and [Just the Docs](https://just-the-docs.github.io/just-the-docs/) theme.

## Local Development

### Requirements
- Ruby 3.0+
- Bundler

### Setup

```bash
cd docs
bundle install
bundle exec jekyll serve
```

Then open [http://localhost:4000](http://localhost:4000) in your browser.

### Building for Production

```bash
bundle exec jekyll build
```

Output will be in the `_site` directory.

## Deployment

This site is deployed to GitHub Pages via the `docs/` folder.

1. Push changes to the `docs/` folder
2. GitHub Actions will automatically build and deploy
3. Your site will be available at `docs.heartrackerr.ca`

## Theme Documentation

For more details on customizing the Just the Docs theme, see the [official documentation](https://just-the-docs.github.io/just-the-docs/).

## Structure

```
docs/
  _config.yml          # Jekyll configuration
  Gemfile              # Ruby dependencies
  index.md             # Home page
  docs/
    api/               # API reference section
    user-manual/       # User guide section
```

## License

Documentation content is available under the MIT License. See repo LICENSE file for details.
