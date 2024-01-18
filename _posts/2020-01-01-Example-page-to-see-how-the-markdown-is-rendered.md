---
title: Example Page to View Markdown Rendering
tags: markdown theme
categories: How-To
toc: true
comments: false
---

# How to use markdown and css style elements

## Abstract block
You can use the `abstract-block` class to create a block with a title and a paragraph. This is useful for creating abstracts, summaries, or TL;DRs.

<div class="abstract-block">
<strong>TL;DR</strong>
<p>We adopted an unpaired neural network training
technique, namely CycleGAN, to generate brightfield
microscope-like images from hologram reconstructions.
The motivation for unpaired training in microscope
applications is that the construction of paired/parallel
datasets is cumbersome or sometimes not even feasible, for example, lensless or flow-through holographic
measuring setups. Our results show that the proposed
method is applicable in these cases and provides comparable results to the paired training. Furthermore, it
has some favorable properties even though its metric
scores are lower. </p>

<p>
The CycleGAN training results in
sharper – from this point of view – more realistic object
reconstructions compared to the baseline paired setting.
Finally, we show that a lower metric score of the unpaired training does not necessarily imply a worse image generation, but a correct object synthesis yet with a
different focepresentation.
</p>
</div>

This is how you can use it in markdown:
```html
<div class="abstract-block">
   <strong>TL;DR</strong>
   <p>Paragraph 1 ... </p>
   <p> Paragraph 2 ...</p>
</div>
```

## Highlighted boxes

You can have different types of highlighted boxes. The following classes are available:
<div class="block info-block">
  <strong>INFO</strong> 

   This is a summary of the article's content. It gives readers a quick overview of what to expect in the full post.
   Our results show that the proposed
   method is applicable in these cases and provides comparable results to the paired training. Furthermore, it
   has some favorable properties even though its metric
   scores are lower.
</div>

```html
<div class="block info-block">
  <strong>INFO</strong>
   ...
</div>
```

<div class="block question-block">
  <strong>QUEST</strong> This is a summary of the article's content. It gives readers a quick overview of what to expect in the full post.
</div>

```html
<div class="block question-block">
  <strong>QUEST</strong>
   ...
</div>
```

<div class="block warning-block">
  <strong>DANGER</strong> This is a summary of the article's content. It gives readers a quick overview of what to expect in the full post.
</div>

```html
<div class="block warning-block">
  <strong>DANGER</strong>
   ...
</div>
```



**Table of Contents**

- [[Headers::#heading]]
- [[Emphasis::#emphasis]]
- [[Lists::#lists]]
- [[Links::#links]]
- [[Images::#images]]
- [[Code and Syntax Highlighting::#syntax]]
- [[Math Expressions::#math]]
- [[Tables::#tables]]
- [[Blockquotes::#blockquotes]]
- [[Inline HTML::#inline]]
- [[Horizontal Rule::#hr]]
- [[Line Breaks::#br]]

### Headings

---

```markdown
# H1

## H2

### H3

#### H4

##### H5

###### H6
```

# H1

## H2

### H3

#### H4

##### H5

###### H6

{:#emphasis}

### Emphasis

---

```markdown
Emphasis, aka italics, with _asterisks_ or _underscores_.

Strong emphasis, aka bold, with **asterisks** or **underscores**.

Combined emphasis with **asterisks and _underscores_**.

Strikethrough uses two tildes. ~~Scratch this.~~
```

Emphasis, aka italics, with _asterisks_ or _underscores_.

Strong emphasis, aka bold, with **asterisks** or **underscores**.

Combined emphasis with **asterisks and _underscores_**.

Strikethrough uses two tildes. ~~Scratch this.~~

{:#lists}

### Lists

```markdown
1. First ordered list item
   ...1. Ordered sublist
2. Another item
   ...\* Unordered sublist
3. Actual numbers don't matter, just that it's a number
4. And another item.

⋅⋅⋅You can have properly indented paragraphs within list items. Notice the blank line above, and the leading spaces (at least one, but we'll use three here to also align the raw Markdown).

⋅⋅⋅To have a line break without a paragraph, you will need to use two trailing spaces.⋅⋅
⋅⋅⋅Note that this line is separate, but within the same paragraph.⋅⋅
⋅⋅⋅(This is contrary to the typical GFM line break behaviour, where trailing spaces are not required.)

- Unordered list can use asterisks

* Or minuses

- Or pluses
```

1. First ordered list item
   1. Ordered sublist
2. Another item
   - Unordered sublist
3. Actual numbers don't matter, just that it's a number
4. And another item.

   You can have properly indented paragraphs within list items. Notice the blank line above, and the leading spaces (at least one, but we'll use three here to also align the raw Markdown).

   To have a line break without a paragraph, you will need to use two trailing spaces.⋅⋅
   Note that this line is separate, but within the same paragraph.⋅⋅
   (This is contrary to the typical GFM line break behaviour, where trailing spaces are not required.)

- Unordered list can use asterisks

* Or minuses

- Or pluses

{:#links}

### Markdown Footnotes

    The quick brown fox[^1] jumped over the lazy dog[^2].

    [^1]: Foxes are red
    [^2]: Dogs are usually not red

Result:
The quick brown fox[^1] jumped over the lazy dog[^2].

[^1]: Foxes are red
[^2]: Dogs are usually not red

### Task Lists

    - [x] @mentions, #refs, [links](), **formatting**, and <del>tags</del> supported
    - [x] list syntax required (any unordered or ordered list supported)
    - [x] this is a complete item
    - [ ] this is an incomplete item

Result:

- [x] @mentions, #refs, [links](), **formatting**, and <del>tags</del> supported
- [x] list syntax required (any unordered or ordered list supported)
- [x] this is a complete item
- [ ] this is an incomplete item


### Links

```markdown
[I'm an inline-style link](https://www.google.com)

[I'm an inline-style link with title](https://www.google.com "Google's Homepage")

[I'm a reference-style link][arbitrary case-insensitive reference text]

[I'm a relative reference to a repository file](../blob/master/LICENSE)

[You can use numbers for reference-style link definitions][1]

Or leave it empty and use the [link text itself].

URLs and URLs in angle brackets will automatically get turned into links.
https://www.example.com or <https://www.example.com> and sometimes
example.com (but not on Github, for example).

Some text to show that the reference links can follow later.

[arbitrary case-insensitive reference text]: https://www.mozilla.org
[1]: https://slashdot.org
[link text itself]: https://www.reddit.com
```

[I'm an inline-style link](https://www.google.com)

[I'm an inline-style link with title](https://www.google.com "Google's Homepage")

[I'm a reference-style link][arbitrary case-insensitive reference text]

[I'm a relative reference to a repository file](../blob/master/LICENSE)

[You can use numbers for reference-style link definitions][1]

Or leave it empty and use the [link text itself].

URLs and URLs in angle brackets will automatically get turned into links.
https://www.example.com or <https://www.example.com> and sometimes
example.com (but not on Github, for example).

Some text to show that the reference links can follow later.

[arbitrary case-insensitive reference text]: https://www.mozilla.org
[1]: https://slashdot.org
[link text itself]: https://www.reddit.com

{:#images}

### Images

```markdown
Here's our logo (hover to see the title text):

Inline-style:
![alt text](/assets/img/profile.png "Logo Title Text 1")

Reference-style:
![alt text][logo]

[logo]: /assets/img/profile.png "Logo Title Text 2"
```

Here's our logo (hover to see the title text):

Inline-style:
![alt text](/assets/img/profile.png "Logo Title Text 1")

Reference-style:
![alt text][logo]

[logo]: /assets/img/profile.png "Logo Title Text 2"

{:#syntax}

### Code and Syntax Highlighting

Code blocks are part of the Markdown spec, but syntax highlighting isn't. However, many renderers -- like Github's and Markdown Here -- support syntax highlighting. Which languages are supported and how those language names should be written will vary from renderer to renderer. Markdown Here supports highlighting for dozens of languages (and not-really-languages, like diffs and HTTPS headers);

```markdown
Inline `code` has `back-ticks around` it.
```

Inline `code` has `back-ticks around` it.

Blocks of code are either fenced by lines with three back-ticks ```, or are indented with four spaces. I recommend only using the fenced code blocks -- they're easier and only they support syntax highlighting.

<pre>
```javascript
var s = "JavaScript syntax highlighting";
alert(s);
```

```python
s = "Python syntax highlighting"
print s
```

```
No language indicated, so no syntax highlighting.
But let's throw in a <b>tag</b>.
```
</pre>

```python
s = "Python syntax highlighting"
print s

@jit(nopython=True, nogil=True)
def generate_bars(timestamp, price, amount):
    n = len(price)

    bar_open = price[0]
    bar_high = price[0]
    bar_low = price[0]
    bar_volume = 0.0
    bar_dvolume = 0.0

    prev_tick_direction = 0
    for i in range(1, n):
        timestamp_i = timestamp[i]
        price_i = price[i]
        amount_i = amount[i]
        dollars_i = price_i * amount_i

        bar_high = max(bar_high, price_i)
        bar_low = min(bar_low, price_i)
        bar_volume += amount_i

        if max_run >= threshold:
            bar_close = price_i
            vwap = bar_dvolume / bar_volume
            
            return timestamp_i, bar_open, bar_high, bar_low, bar_close, bar_volume, vwap

    return None
```

```
No language indicated, so no syntax highlighting.
But let's throw in a <b>tag</b>.
```

### Math

You can write math expressions using the $$LateX$$ [markup language](https://en.wikipedia.org/wiki/LaTeX) between double dollar signs : `$$...$$`. They can be written inline or as a single block.

For example, `$$P(A|B) = \frac{P(B | A)\cdot P(A)}{P(B)}$$` will render as:

$$P(A|B) = \frac{P(B | A)\cdot P(A)}{P(B)}$$

Please note that for a math block to be displayed correctly, it needs to be separated by an empty line, above and below. Besides, the pipe character `|` may conflict with markdown: it is recommended to use `\vert` instead.

### Tables

Tables aren't part of the core Markdown spec, but they are part of GFM and Markdown Here supports them. They are an easy way of adding tables to your email -- a task that would otherwise require copy-pasting from another application.

```markdown
Colons can be used to align columns.

| Tables        |      Are      |   Cool |
| ------------- | :-----------: | -----: |
| col 3 is      | right-aligned | \$1600 |
| col 2 is      |   centered    |   \$12 |
| zebra stripes |   are neat    |    \$1 |

There must be at least 3 dashes separating each header cell.
The outer pipes (|) are optional, and you don't need to make the
raw Markdown line up prettily. You can also use inline Markdown.

| Markdown | Less      | Pretty     |
| -------- | --------- | ---------- |
| _Still_  | `renders` | **nicely** |
| 1        | 2         | 3          |
```

Colons can be used to align columns.

| Tables        |      Are      |   Cool |
| ------------- | :-----------: | -----: |
| col 3 is      | right-aligned | \$1600 |
| col 2 is      |   centered    |   \$12 |
| zebra stripes |   are neat    |    \$1 |

There must be at least 3 dashes separating each header cell.
The outer pipes (|) are optional, and you don't need to make the
raw Markdown line up prettily. You can also use inline Markdown.

| Markdown | Less      | Pretty     |
| -------- | --------- | ---------- |
| _Still_  | `renders` | **nicely** |
| 1        | 2         | 3          |

{:#blockquotes}

### Blockquotes

```markdown
> Blockquotes are very handy in email to emulate reply text.
> This line is part of the same quote.

Quote break.

> This is a very long line that will still be quoted properly when it wraps. Oh boy let's keep writing to make sure this is long enough to actually wrap for everyone. Oh, you can _put_ **Markdown** into a blockquote.
```

> Blockquotes are very handy in email to emulate reply text.
> This line is part of the same quote.

Quote break.

> This is a very long line that will still be quoted properly when it wraps. Oh boy let's keep writing to make sure this is long enough to actually wrap for everyone. Oh, you can _put_ **Markdown** into a blockquote.

Inline HTML

You can also use raw HTML in your Markdown, and it'll mostly work pretty well.

```html
<dl>
  <dt>Definition list</dt>
  <dd>Is something people use sometimes.</dd>

  <dt>Markdown in HTML</dt>
  <dd>Does *not* work **very** well. Use HTML <em>tags</em>.</dd>
</dl>
```

You can also use raw HTML in your Markdown, and it'll mostly work pretty well.

<dl>
  <dt>Definition list</dt>
  <dd>Is something people use sometimes.</dd>

  <dt>Markdown in HTML</dt>
  <dd>Does *not* work **very** well. Use HTML <em>tags</em>.</dd>
</dl>

{:#hr}

### Horizontal Rule

Three or more hypens `---`, underscores `___`, or asterisks `***`.

___


### Line Breaks

```
Here's a line for us to start with.

This line is separated from the one above by two newlines, so it will be a *separate paragraph*.

This line is also a separate paragraph, but...
This line is only separated by a single newline, so it's a separate line in the *same paragraph*.
```

Here's a line for us to start with.

This line is separated from the one above by two newlines, so it will be a _separate paragraph_.

This line is also a separate paragraph, but...
This line is only separated by a single newline, so it's a separate line in the _same paragraph_.

License: CC-BY
