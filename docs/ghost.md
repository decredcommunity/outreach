---
author: bee
published_utc: 2022-12-23
---

# Ghost

[Decred Magazine](https://www.decredmagazine.com/) runs on [Ghost](https://ghost.org/) so we need to know its gotchas.


## Text size

Limitations:

- Featured text: 300 characters
  - Shown under post title on some pages ([example](https://www.decredmagazine.com/tag/articles/)).


## Image size

> For my featured images I use these settings: Width = 2,560 px, Height = 1,440px, JPEG quality = 90%, Max quality = 500 KB but prefer 200-300 KB, left/right bleed = 250 px. Hope this helps. These settings also work pretty well for YouTube and Twitter. \[@phoenixgreen\]

"left/right bleed" here means the outer area of the image that has no important parts or details. In other words, logo, title and other important parts should be at least 250 px away from the edge. This way nothing valuable is lost in different contexts where the image may be slightly cropped.


## Markdown

1\. Manually fix bullet lists with extra blanks between items.

Example. Ghost seems to render this:

```
- Item one.

- Item two.
```

Like this:

```
Item one.

Item two.
```

Blanks between items are useful to make each item more visible. In Ghost these need to be manually adjusted.

2\. Fix multi-line quote blocks.

These:

```
> Quoted paragraph 1.
> 
> Quoted paragraph 2.
```

May get rendered as two separate quote blocks instead of one connected block. If this happens, try the following:

- Add right angle bracket followed by a space (`> `) between quoted paragraphs to connect them.
- If that didn't work, try `> &nbsp;` instead.

3\. Local links like `[other doc](other-doc.md)` must be fixed manually.


## Other

4\. Add relevant tags. Your post will be shown on that tag's page.

5\. Featured image specifics

Logo and text overlay must not be too close to image border, or it may get cut off in some layouts.

6\. Add summary text.

It is shown under post title on various pages.


## Links to subheadings

Links to headings are generated from Markdown headings automatically. Naming algorithm is identical to [GitHub Pages](platforms.md#links-to-subheadings).
