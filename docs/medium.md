---
author: bee
published_utc: 2022-12-23
---

# Medium

Tips for publishing on [Medium](https://medium.com/).


## Text size

Limitations:

- Summary text: 140 characters
  - This is shown under post title ([example](https://medium.com/decred)) and on listing pages ([example](https://medium.com/decred/journals/home)).


## Image size

- 1400x700 px (2:1) is a good choice.
- The editor supports images up to 25 MB in the .JPG, .JPEG, .GIF, and .PNG formats.
- Images should have a minimum width of 692 px to ensure the image completely spans the story page, and the image is consistently formatted for all story previews.

Medium help:

- [Using images](https://help.medium.com/hc/en-us/articles/215679797-Using-images)
- [ Publication images ](https://help.medium.com/hc/en-us/articles/115004979188-Publication-images)


## Markdown

Medium does not support Markdown directly and instead has its own rich editor. However, it is still possible to keep your docs in Markdown and publish them on Medium in a few quick steps.

**Posting Markdown on Medium** methods:

- Rendered your Markdown as rich text elsewhere, then copy and paste it into Medium's editor (simplest).
  - e.g. post your Markdown in [Gists](https://gist.github.com/), a normal GitHub repo, or your GitHub Pages site (requires GitHub account).
- Use an offline converter like [this](https://github.com/yoshuawuyts/markdown-to-medium).
- Use an online service like [this](http://markdowntomedium.com/).

**Gotchas**

1\. Avoid complex Markdown that does not paste cleanly into Medium editor:

- Paragraph breaks and blockquotes inside list items. Keep list items simple.
- Nested lists.
- In general, avoid combining _any_ two structural features to be extra safe.
- Two adjacent blockquotes are merged in one if they are not separated by normal text. Try adding more blank lines to break them.

If you really want to use advanced Markdown features (e.g. on GitHub), prepare a separate, simplified Markdown file for Medium that work-arounds all Medium's formatting issues.

2\. Local links like `[other doc](other-doc.md)` must be fixed manually.

3\. Table of Contents must be recreated manually in the Medium editor (there may be plugins for this).


## Other

4\. Add relevant tags.

Some tags relevant for Decred:

- https://medium.com/tag/decred
- https://medium.com/tag/cryptocurrency
- https://medium.com/tag/decentralized-exchange
- https://medium.com/tag/cryptocurrency-news
- https://medium.com/tag/crypto

5\. Fill the summary text.


## Links to subheadings

Medium generates anchors that can be used to link to specific places of the document. Unlike [GitHub Pages](platforms.md#links-to-subheadings):

- Anchors are 4 character long and are not derived from the heading.
- Anchors are created for each paragraph and not only for headings.
- See Table of Contents [here](https://medium.com/decred/decred-journal-november-2022-3be533057e86#44be) for an example.
