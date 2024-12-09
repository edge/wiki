---
description: >-
  Governance proposals are actively encouraged and are open for anyone with a
  governance stake. There is a standard format for proposals that should be
  followed, which is described here.
---

# Proposal Guidelines

## Proposal Structure

The structure of a proposal is simple, and consists of `Title` and `Proposal detail`. These are separate input boxes on the `Draft Proposal` screen.

The `Title` maps to an H1 tag in HTML.

The `Proposal detail` is markdown formatted. Headings within this section should be H2, H3 etc. (i.e. not H1, as this is used for the title.) A markdown code reference can be seen below.

Proposals must be at least 500 characters (between 70 and 125 words with spaces included). This threshold is set to ensure that a minimum level of clarity is provided. This threshold is enforced, and you won't be able to advance to preview your proposal until the minimum requirement is met.

_Note: proposals are submitted to the XE Blockchain and are permanent. Once submitted they cannot be changed_

### Proposal Detail

The structure of the proposal detail should match the following structure:

1. Summary
2. Proposal detail
3. Rationale

The **Summary** should provide a general introduction/overview to your proposal in a sentence or two (and no more than two paragraphs).

The **Proposal detail** should set out the detail of your proposal, and contain specific details about what the proposal would do and achieve if implemented. At the end of the proposal detail you should set out the key points as a summarised bullet list, as follows:

`It is proposed that:`

* `Item 1`
* `Item 2`
* `Item 3`
* `...`

The **Rationale** should lay out the reasons for, and benefits of, your proposal.

#### Real World Example

A good example of this structure can be found here:

{% embed url="https://governance.edge.network/proposal/cd0cd6f364370119133c830ac4d435b28df41ab96cb12d6a1997cc2e12d68b81" %}

## Markdown Reference

The following reference covers the markdown styling that is supported in the governance system. This is a subset of the markdown reference. The system will remove items such as images and inline HTML to help to keep goverance clean and spam free.

### Headers

```
## H2
### H3
```

### H2

#### H3

### Emphasis

```
Emphasis, aka italics, with *asterisks* or _underscores_.

Strong emphasis, aka bold, with **asterisks** or __underscores__.

Combined emphasis with **asterisks and _underscores_**.
```

Emphasis, aka italics, with _asterisks_ or _underscores_.

Strong emphasis, aka bold, with **asterisks** or **underscores**.

Combined emphasis with **asterisks and&#x20;**_**underscores**_.

### Lists

```
1. First ordered list item
2. Another item
    1. Ordered sub-list
    2. Another item
3. Actual numbers don't matter, just that it's a number
4. Ordered sub-list
    - Unordered sub-list
    - Another item
5. And another item
```

1. First ordered list item
2. Another item
   1. Ordered sub-list
   2. Another item
3. Actual numbers don't matter, just that it's a number
4. Ordered sub-list
   * Unordered sub-list
   * Another item
5. And another item

### Links

Note that links are automatically extracted into a references section at the end of the proposal.

```
[I'm an inline-style link](https://www.google.com)

[I'm a relative reference to a repository file](../blob/master/LICENSE)
```

I'm an inline-style link\[1]

I'm a relative reference to a repository file\[2]

#### References <a href="#references" id="references"></a>

1. https://www.google.com
2. ../blob/master/LICENSE

### Code and Syntax Highlighting

```
Inline `code` has `back-ticks around` it.
```

Inline `code` has `back-ticks around` it.

````
```
var s = "Here's an extended code block";
alert(s);
```
````

```
var s = "Here's an extended code block";
alert(s);
```

### Blockquotes

```
> Blockquotes are very handy in email to emulate reply text.
> This line is part of the same quote.

Quote break.

> This is a very long line that will still be quoted properly when it wraps. Oh boy let's keep writing to make sure this is long enough to actually wrap for everyone. Oh, you can *put* **Markdown** into a blockquote. 
```

> This is a very long line that will still be quoted properly when it wraps. Oh boy let's keep writing to make sure this is long enough to actually wrap for everyone. Oh, you can _put_ **Markdown** into a blockquote.

Quote break.

> Blockquotes are very handy in email to emulate reply text. This line is part of the same quote.

### Horizontal Rule

```
Three or more...

---

Hyphens

***

Asterisks

___

Underscores
```

_Note: Gitbook doesnt support horizontal rules in macdown, so a preview isn't available_

### Line Breaks

```
Here's a line for us to start with.

This line is separated from the one above by two newlines, so it will be a *separate paragraph*.

This line is also a separate paragraph, but...
This line is only separated by a single newline, so it's a separate line in the *same paragraph*.
```

Here's a line for us to start with.

This line is separated from the one above by two newlines, so it will be a _separate paragraph_.

This line is also begins a separate paragraph, but...\
This line is only separated by a single newline, so it's a separate line in the _same paragraph_.
