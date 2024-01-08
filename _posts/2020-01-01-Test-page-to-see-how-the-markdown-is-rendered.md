---
title: Example Page to View Markdown Rendering
tags: markdown
toc: true
comments: true
---

## Philosophy:

<div class="abstract-block">
  <strong>Abstract:</strong>
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

```html
<div class="abstract-block">
  <strong>Abstract:</strong>
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
```

<div class="block info-block">
  <strong>Info:</strong> This is a summary of the article's content. It gives readers a quick overview of what to expect in the full post.
</div>

<div class="block question-block">
  <strong>Question:</strong> This is a summary of the article's content. It gives readers a quick overview of what to expect in the full post.
</div>

<div class="block warning-block">
  <strong>Danger Zone:</strong> This is a summary of the article's content. It gives readers a quick overview of what to expect in the full post.
</div>


To this end, Markdown’s syntax is comprised entirely of punctuation characters, which punctuation characters have been carefully chosen so as to look like what they mean. E.g., asterisks around a word actually look like _emphasis_. Markdown lists look like, well, lists. Even blockquotes look like quoted passages of text, assuming you’ve ever used email. This is intended as a quick reference and showcase.

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

```javascript
var s = "JavaScript syntax highlighting";
alert(s);
```

```python
s = "Python syntax highlighting"
print s

@jit(nopython=True, nogil=True)
def generate_dollar_runbars(timestamp, price, amount, threshold, scaling_factor=1.0):
    n = len(price)

    cum_pos_dollars = 0.0
    cum_neg_dollars = 0.0
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
        tick_direction = np.sign(price[i] - price[i-1])

        if tick_direction == 0:
            tick_direction = prev_tick_direction

        if tick_direction == 1:
            cum_pos_dollars += dollars_i
            prev_tick_direction = 1
        else:
            cum_neg_dollars += dollars_i
            prev_tick_direction = -1

        max_run = max(cum_pos_dollars, cum_neg_dollars)

        bar_high = max(bar_high, price_i)
        bar_low = min(bar_low, price_i)
        bar_volume += amount_i
        bar_dvolume += dollars_i

        if max_run >= (threshold * scaling_factor):
            bar_close = price_i
            vwap = bar_dvolume / bar_volume
            
            return timestamp_i, bar_open, bar_high, bar_low, bar_close, bar_volume, vwap, i

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

My basic recommendation for learning how line breaks work is to experiment and discover -- hit <Enter> once (i.e., insert one newline), then hit it twice (i.e., insert two newlines), see what happens. You'll soon learn to get what you want. "Markdown Toggle" is your friend.

Here are some things to try out:

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
