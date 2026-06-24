# CLAUDE.md — Nightingale

## Current task

> Note: the following syntax (@file) includes the specified file into context, see https://code.claude.com/docs/en/memory#import-additional-files.

@TASK

## Your role

Your task is to assist the user in writing stories. It is intended that most of the actual content, and especially the final version, is written by the user. However, you should support the user in the processing of information and in ensuring adherence to the format requirements as well as the writing style preferences stated in this document.

## About this repository

Currently, Nightingale serves as a central location for developing, collecting and publishing stories.

A story is any standalone text that may be published as, for example, an article.

### Directory structure

```
drafts/     # Work-in-progress stories
finished/   # Finished stories
```

Each story in `drafts/` or `finished/` is a directory with the following structure:

```
story-title/     # Internal identifier of the story
  index.md       # Content of the story
  aux.png        # Assets and other aux files used by the story
  ...
```

Stories are started in the `drafts/` directory and moved to the `finished/` directory when they are finished and ready for publication.

> Note: some stories in `drafts/` additionally contain a `metadata.legacy.yaml` file containing "created" and "last updated" dates. These are the dates from the previous legacy file formats and are just included for completeness. It's still to be determined whether these dates will be used at all. The `metadata.legacy.yaml` should eventually be deleted.

## Format requirements

### `index.md`

- Pure Markdown, no YAML frontmatter
- Starts with a `#` heading with the title of the story
- References assets with relative paths (e.g. `./aux.png`)

### Story directory name

- Kebab-case
- Internal identifier of the story it contains
- Ideally corresponds to the story title but deviations are allowed (e.g. if the story title is very long)
- May be udpated (e.g. to more closely match the story title) for stories in the `drafts/` folder
- Must not be updated for stories in the `finished/` folder

## Writing

Most of the actual writing is done by the user, but as an agent, you should ensure that the following preferences are followed where possible.

### Writing style preferences

- Write for an interested tech-savvy audience
- Use clear chains of reasoning rather than fuzzy clouds of observations
- Prefer "insight first, then details" organisation (e.g. per section) rather than chronological lists of details
- Use common threads that run throughout a story and that guide readers through
- Convey clear points that can be remembered by readers after reading a story
- Prefer conciseness, avoid repetition
- Be very consistent with terminology (e.g. use the same terms for the same concepts throughout)

### Writing process

1. Start by defining the concepts that the story is about
2. Settle on a precise terminology for these concepts
3. Define the relations between the individual concepts (e.g. causatio, etc.)
4. Gradually add content around the skeleton of concepts and their relations

## Story ideas

Ideas for future stories are tracked in GitHub Issues, not in repository files.

## Future work

- Merging in legacy notes content: there is a set of old notes repositories (see the [Notes Repository Consolidation](https://github.com/users/weibeld/projects/69?pane=issue&itemId=202722447) project). There may be content that can be moved from these notes repositories to the files about the same topic in this repository. Also check whether other content may be transformed into a story in this repository.
- Publishing pipeline: use this repoitory as the source for a publishing pipeline that publishes finsished stories to one or more destinations, like a website (e.g. through an SSG) or a platform like Medium. The publishing pipeline is read-only and the single source of truth of the stories remains in this repository.
- Metadata extraction: extract metadata about stories, in particular the 'created' date and the 'last edited' date from the Git history (if necessary, use `git log --follow` to track directory renames)
