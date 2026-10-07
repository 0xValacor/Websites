# Instructions for agents

## Every page must be linked from index.html

`index.html` is the list of all pages on this site. Whenever you add a new page (any new `.html` file other than `index.html`), you must also add a link to it in `index.html` as part of the same change. A page is not finished until it appears in that list.

Likewise, if you rename or delete a page, update or remove its entry in `index.html`.

### How to add an entry

Copy an existing `<li class="work">` block inside `<ol class="works">` in `index.html`, append it at the end of the list, and change:

- `href`: the new page's filename.
- `.num`: the next number in sequence, two digits (`03`, `04`, …).
- `.title`: the page's name.
- `.sub`: a short subtitle.
- `--accent` / `--accent-soft`: the page's main color as hex, and the same color as `rgba(…, .18)`.

```html
<li class="work" style="--accent: #ffd319; --accent-soft: rgba(255,211,25,.18)">
  <a href="newpage.html">
    <span class="num">03</span>
    <span class="title">NEW PAGE<span class="sub">short subtitle</span></span>
  </a>
</li>
```

Keep `index.html` plain: just the list of links, no animations and no JavaScript.

### Check before finishing

Every `.html` file in the root except `index.html` must have exactly one matching `href` in `index.html`. This command prints any page that is missing:

```sh
for f in *.html; do [ "$f" = index.html ] || grep -q "href=\"$f\"" index.html || echo "missing: $f"; done
```
