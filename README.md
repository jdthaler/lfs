# Large files for jthaler.net

Public file host for [jthaler.net](https://jthaler.net/). Files here are stored
in Git LFS and linked from the site.

Currently: **`talks/`** — slides from talks, colloquia, lectures and seminars by
[Jesse Thaler](https://jthaler.net/), MIT. Browse them in context at
<https://jthaler.net/cv/#presentations>, which lists each one with its event,
venue and date. This repository is the file host behind those links, not the
index.

## Why the files are not on the site itself

GitHub Pages does not resolve Git LFS — it serves the pointer file rather than
the PDF. So links on jthaler.net do not point at the site; they point at this
repository's raw endpoint, applied by a single `talks_base_url` setting in the
site's `_config.yml`.

This is a repository of its own because the site's source is private, and a
private repository's raw endpoint requires authentication, which broke every
talk link. Only these files are public.

## Adding another category

Put it in its own top-level folder. `.gitattributes` sends every `*.pdf` to LFS
whatever the folder; other large file types need their own rule added there
before the first commit that includes one, or they land in git proper and are
awkward to remove afterwards.

The site resolves a link by looking at the first directory in the path, so a new
folder also needs teaching to `_includes/snippets/get-talk-url.html`.

## Reusing anything here

Shared for reference and teaching. To reuse a figure, please ask:
<jthaler@mit.edu>.
