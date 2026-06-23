# CLAUDE.md — Writing

## About

This repository serves as a central location for developing, collecting and publishing write-ups.

A write-up is any standalone text that may be published as, for example, an article.

## Directory structure

```
drafts/     # Work-in-progress write-ups
published/  # Finished write-ups
```

Each write-up in `drafts/` or `published/` is a directory with the following structure:

```
write-up-title/  # Title of the write-up in kebab-case
  index.md       # Main content of the write-up
  diagram.png    # Assets used by the write-up
  ...
```

Notes:

- The directory name of a write-up ideally corresponds to the write-up's title (as defined in `index.md`) in kebab-case. However, if the title of a write-up changes, the directory does not need to be automatically renamed.

## Content structure

- `index.md` is a pure Markdown file and should start with a `#` heading defining the title of the write-up
- `index.md` should not contain any metadata (e.g. dates, IDs) in a YAML frontmatter or in any other form
- Assets are referenced with relative paths (e.g. `./diagram.png`)

## Write-up ideas

Ideas for future write-ups are tracked in GitHub Issues, not in repository files.

## Future extensions

In a future stage, this repo may serve as the source for a publishing pipeline that publishes finalised write-ups to one or more destinations, such as a website (e.g. through an SSG) or a platform like Medium. However, the single source of truth of all write-ups is intended to remain in this repository.
