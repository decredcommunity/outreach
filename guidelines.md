# Decred Journal Production Guidelines

## Style, Editing

### Use canonical links without tracking

First, remove any tracking parameters like Medium's `gi=...`, Google Analytics `utm_...`, etc. As a general rule, remove any URL parameters that don't break the link. "URL parameters" is the stuff that comes after `?` in the URL.

Second, ensure URLs are [canonical](https://en.wikipedia.org/wiki/Canonical_link_element). This means using www.reddit.com over old.reddit.com, www.youtube.com over youtu.be, and so on. On most pages canonical link can be found in `<link rel="canonical" href="..."/>` in the page source. Use of canonical links improves linking of content together (e.g. on Reddit).

**Examples**

Bad: junk parameters: https://www.youtube.com/watch?v=3RGoUQK0g24&feature=share

Bad: non canonical domain: https://youtu.be/3RGoUQK0g24

Good: https://www.youtube.com/watch?v=3RGoUQK0g24

Bad: Forbes tracking (remove the `#425f36a11067`):

https://www.forbes.com/sites/kenrapoza/2019/06/20/facebooks-libra-coin-is-both-vampire-project-and-regulatory-nightmare/#425f36a11067

Bad: Medium tracking (remove the `?gi=68a95d076f04`):

https://hackernoon.com/decred-wants-you-be-one-of-the-first-to-test-the-dcr-lightning-network-dd9ecf14d95e?gi=68a95d076f04

### Markdown

- Use backslash `\` to escape underscore `_` so it won't be treated as italics. Example: `under\_score`.
- Always use hyphen `-` for bullet lists.
- Always use `_underscore_` for italics and `**double asterisk**` for bold.

See this excellent [cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet) of Markdown features.

Medium/Odysee/etc versions may require additional processing to look nice. It is recommended that the "Git/Markdown maintainer" role does as much Markdown preparation as possible, and places the final files in a well-known location (e.g. [decred-journal-extra](https://github.com/xaur/decred-journal-extra)) so that Medium/Odysee admins can just copy-paste it without torture (be nice with them, we don't have many).

**Medium specifics**

1\. Avoid Markdown features that cause trouble when pasting into Medium:

- Paragraph breaks and blockquotes inside list items.
- Nested lists.
- In general, avoid combining _any_ two structural formatting features to be extra safe.

If you really want to use advanced Markdown features that "just work" on GitHub, please prepare a separate, simplified Markdown file for Medium that work-arounds all Medium's formatting issues.

2\. Table of Contents must be recreated manually.

**Odysee specifics**

1\. Replace all "simple" usages of the `@` character with its HTML escape sequence `&#64;`.

  - "Simple" usages are the ones NOT inside link text (e.g. `[@HotUser](url...)`), NOT coming after a square bracket (e.g. `\[@HotUser, bla bla\]` seems to work), and NOT inside link URLs (e.g. `[bla bla](https://medium.com/@username/...)`).

  - Why: Odysee Markdown renderer tries to automatically create links on `@username`-s. Problems - it may tag or even notify an unintended person, and it adds ugly paragraph breaks.
