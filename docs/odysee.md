---
author: bee
published_utc: 2022-12-23
---

# Odysee

Tips for publishing on [Odysee](https://odysee.com/).


## Markdown

1\. Replace all "simple" usages of the `@` character with its HTML escape sequence `&#64;`.

  - "Simple" usages are the ones NOT inside link text (e.g. `[@HotUser](url...)`), NOT coming after a square bracket (e.g. `\[@HotUser, bla bla\]` - `@` is fine here), and NOT inside link URLs (e.g. `[bla bla](https://medium.com/@username/...)` - `@` is fine here).

  - Why: Odysee Markdown renderer tries to automatically create links on `@username`-s. Problems - it may tag or even notify an unintended person, and it adds ugly paragraph breaks.

2\. Convert local links to images to absolute links.

Example: `![](../img/202207.1.github.png)` -> `![](https://xaur.github.io/decred-news/img/202207.1.github.png)`.

3\. Convert local links to posts to absolute links.

Example: `[see June issue](202206.md)` -> `[see June issue](https://odysee.com/@Decred:c/decred-journal-2022-06:8)`.


## Other

4\. When publishing, pay attention to post ID. It cannot be changed later.

For example, DJ sticks to pattern `decred-journal-YYYY-MM`. Adjust for your post or post series.
