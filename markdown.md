# Markdown <!-- omit in toc -->

Markdown is a lightweight markup language that is used to create formatted text through a plaintext editor. Markdown is intended a writing language, as opposed to publishing language such as HTML, thus it is very readable, i.e. its formatting can be read in the absent of tags or formatting instructions like those in RTF or HTML.

## Table of Contents <!-- omit in toc -->

- [Usage](#usage)
- [Writing in Markdown](#writing-in-markdown)
  - [Hard-wrapped](#hard-wrapped)
  - [Special Characters](#special-characters)
- [Formattings](#formattings)
  - [Header](#header)
  - [Lists](#lists)
    - [Unordered Lists](#unordered-lists)
    - [Ordered Lists](#ordered-lists)
  - [Emphasis](#emphasis)
  - [Inline Code](#inline-code)
  - [Blockquotes](#blockquotes)
  - [Links](#links)
  - [Images](#images)
  - [Local Hyperlink](#local-hyperlink)
  - [Horizontal Rules](#horizontal-rules)
- [Github Flavored Markdown](#github-flavored-markdown)
  - [Strikethrough](#strikethrough)
  - [Syntax Highlighting](#syntax-highlighting)
  - [Task List](#task-list)
  - [Tables](#tables)
- [Converting Markdown](#converting-markdown)
- [Linting](#linting)
- [Creating Table of Contents](#creating-table-of-contents)

## Usage

Markdown is widely used in readme files, forum & blog posts, and static site generators. Aside from those, Markdown is also widely used for academic writing, but such matter is outside the scope of this article.

## Writing in Markdown

Before we get to the brass tacks, there are several important concepts in writing a markdown document that you need to grasp.

### Hard-wrapped

Markdown supports hardwrapped text paragraphs, i.e. one could manually decide the width of a paragraph in the plaintext writing. This also means that any line breaks can't be represented by a simple end of line. Instead, paragraphs or lines can be represented by a blank line inbetween it's plaintext writing.

Example:

This is the
first paragraph

This is the second one

Syntax:

```md
This is the
first paragraph

This is the second one
```

### Special Characters

Markdown treats characters that is treated in a special manner in HTML, less-than sign (<) and ampersand (&), naturally, i.e. markdown automatically translate an '&' into \&amp; and an '<' into \&lt; while also supports writing it in the opposite manner.

As a markup language, markdown also have its own syntax. Which begs the question, how could one write the symbols that is used for markdown syntax? Fortunately, the answer is rather simple, that is you could just prepend a backslash before any such symbols.

Example:

& &amp; \&amp;

\## This is not a header

\\## A backlash is also a syntax symbol

Syntax:

```md
& &amp; \&amp;

\## This is not a header

\\## A backlash is also a syntax symbol
```

## Formattings

One of the things one would expect from a markup language is, of course, the ability for basic formattings. Core Markdown provides an ample list of such formattings.

### Header

See how previous text's fonts changes sizes? That's headers doing their work. You can create a header by preeciding a line with number sign(s) and a space ("## "). As seen above, headers come in multiple levels with the amount of number sign indicating the level of a header. Aside from that, headers can also be implemented in Setext-style, i.e. by underlining a line with at least three equal signs (=) or dashes (-). Although, it is much more complicated and inneficient.

Example:

# This is a first level header <!-- omit in toc -->

## This is a second level header <!-- omit in toc -->

### This is a third level header <!-- omit in toc -->

#### This is a fourth level header <!-- omit in toc -->

##### This is a fifth level header <!-- omit in toc -->

###### This is a sixth level header <!-- omit in toc -->

This is also a first level header <!-- omit in toc -->
===

This is also a second level header <!-- omit in toc -->
---

```md
# This is a first level header
## This is a second level header
### This is a third level header
#### This is a fourth level header
##### This is a fifth level header
###### This is a sixth level header

This is also a first level header
===
This is also a second level header
---
```

### Lists

The need for lists, be it for either an ordered one or an unordered one, often appear while writing in a markup language, which is why markdown has provided the means to create as many as needed.

#### Unordered Lists

To create an unordered lists you may choose between adding a dash (-) or an asterisk (*) before a line as you see fit. Lists could also be made to include up to three levels by indenting a line with tab(s) or space(es).

Example:

- First item in the first level
- Second item in the first level
  - First item in the second level
    - First item in the third level
- Third item in the first level

Syntax:

```md
- First item in the first level
- Second item in the first level
  - First item in the second level
    - First item in the third level
- Third item in the first level
```

#### Ordered Lists

Ordered lists can be created by prepending a number in which you want the list numbering to start from. Unfortunately, while you can make ordered list into several levels, the numbering system only allows arabic numbers that goes in sequential order. The syntax, however, does not require you to manually increment each numbers.

Example:

1. First item in the first level
2. Second item in the first level
   1. First item in the second level
      1. First item in the third level
3. Third item in the first level

Syntax:

```md
1. First item in the first level
2. Second item in the first level
   1. First item in the second level
      1. First item in the third level
3. Third item in the first level
```

### Emphasis

Another important aspect in text formatting is emphasizing a word or several. Core markdown provides two types of emphasis; bold and italic. To bold words or characters, you can simply put aforementioned word(s) or character(s) inbetween two asterisks (*) or underlines (_).

Example:

Which of the following statements is **not** true?

_Et tu, Bruté?_—Then fall, Caesar.

You could also nest ***italics* in a bolded sentence**, or *vice **versa***

Syntax:

```md
Which of the following statements is **not** true?

_Et tu, Bruté?_—Then fall, Caesar.

You could also nest ***italics* in a bolded sentence**, or *vice **versa***
```

### Inline Code

Another feature included in core markdown is the ability to include a string of code inside a line. It can be done by wrapping the string of code with apostrophes (').

Example:

I think you should use an
`<addr>` element here instead.

Syntax:

```md
I think you should use an
`<addr>` element here instead.
```

### Blockquotes

Blockquotes is, well, blocked quotes. Such feature can be applied by preceeding a line with a greater than symbol followed by a space ("> "). Like lists, blockquotes could also be nested.

Example:

> As Kanye West said:
>
>> We're living the future so the present is our past.

Syntax:

```md
> As Kanye West said:
>
>> We're living the future so the present is our past.
```

### Links

In creating a useful writing, the absence of links to a website is not a common sight. Thus, to incorporate hyperlinks into your writing, you could put the soon-to-be hyperlink word inside a square bracket and put the link inside a parentheses next to it. Link definitions can be placed anywhere in your Markdown document, although placing it next to the hyperlinked word(s) is the common practice. I'd really love to explain how these work, but i think you would have an easier time by looking at the example below.

Example:

[Google][1]

[Yahoo Search]([www.yahoo.com](http://search.yahoo.com/))

[MSN][]

[1]: http://google.com/
[msn]: http://search.msn.com/

Syntax:

```md
[Google][1]

[Yahoo Search]([www.yahoo.com](http://search.yahoo.com/))

[MSN][]

[1]: http://google.com/
[msn]: http://search.msn.com/
```

### Images

In this day and age, many documents also include images attached to them. Not wanting to be left behind, markdown also allow images to be included on a file, albeit requiring said image to be hosted on external website, through manner similiar to hyperlinks, but with an exclamation mark (!) preceeding it.

Example:

![WW2 French flag](https://i.pinimg.com/originals/4b/b5/7a/4bb57a18a191dd55ca100560e6e91fd1.png)

Syntax:

```md
![WW2 French flag](https://i.pinimg.com/originals/4b/b5/7a/4bb57a18a191dd55ca100560e6e91fd1.png)
```

### Local Hyperlink

See the ToC at the top of the page? That ToC does not require an intricate configuration to setup, instead it consisted only of multilevel [unordered lists](#unordered-lists) and, of course, a [hyperlink](#local-hyperlink) to the respective position of each points.

Syntax:

```md
See the ToC at the top of the page? That ToC does not require an intricate configuration to setup, instead it consisted only of multilevel [unordered lists](#unordered-lists) and, of course, a [hyperlink](#local-hyperlink) to the respective position of each points.
```

### Horizontal Rules

Sometimes, it is desirable to divide a text with a horizontal line as an extra measure to the use of headers. Although it pains me to ruin this text's artistically curated aesthetic for such a simple and graceless exhibition, i will include below the example of horizontal rule by adding at least three asterisks (*) or dashes (-), which i hope you will only imitate in a situation oposite of mine.

Example:

***

Syntax:

```md
***
```

## Github Flavored Markdown

### Strikethrough

To make any word to appear crossed out for whatever reason, you could surround it with two tildes ("~~") on each sides.

Example:

There's still ~~a lot of~~ mistakes to be corrected.

Syntax:

```md
There's still ~~a lot of~~ mistakes to be corrected.
```

### Syntax Highlighting

The blocks of codes in this text uses syntax highlighting, which is—in fact—a feature from github featured markdown, that can be implemented by writing lines which include three backticks (`) before and after a block of code. In the first line of backticks, you could add the language in which the aforementioned code is written.

Example:

```py
for i in range(5):
  print(i)
```

Syntax:

```md
```py
for i in range(5):
  print(i)
‎```
```

### Task List

Exceptionally useful as a progress indicator for your issue listm task list can be implemented by creating a regular list, be it ordered or unordered, and prepending each items with an empty square bracket ("[ ]"), for an unchecked list, or a square bracket with the letter 'X' between them ("[X]"). Task list can also be multi-leveled.

Example:

- [x] Clean the house
  - [x] Mop the floor
  - [X] Dust the shelves
- [x] Cook dinner
- [ ] Commit war crimes

Syntax:

```md
- [x] Clean the house
  - [x] Mop the floor
  - [X] Dust the shelves
- [x] Cook dinner
- [ ] Commit war crimes
```

### Tables

Another important but likely overlooked feature is the ablility to create tables by assembling a list of words and dividing them with hyphens (-) (for the table header row), and then separating each column with a pipe |.

Example:

First Header | Second Header
------------ | -------------
Content from cell 1 | Content from cell 2
Content in the first column | Content in the second column

Syntax:

```md
First Header | Second Header
------------ | -------------
Content from cell 1 | Content from cell 2
Content in the first column | Content in the second column
```

## Converting Markdown

As previously mentioned, markdown can be converted to HTML for a nice static web page (or parts of it). Aside from that, markdown could also be converted into other formats, such as PDF. However, converting to pdf requires you to add additional metadatas at the start of the documents. To do so, you could use Pandoc, which is available in command line, or you could use online converter, which may be limited in terms of features.

To use `pandoc` in CLI, you may need to install it first. Its usage is very versatile. If no input file is specified, input is read from stdin. While stdout is the default output, you could also output to a file. As for online tools, there is a phletora of websites which provides markdown conversion services, such as  [CloudConvert](https://cloudconvert.com/md-to-html), [Try Pandoc](https://pandoc.org/try), and [browserling](https://www.browserling.com/tools/markdown-to-html).

## Linting

To create a level of standardized consistency, you could use markdown linting tools. While there's a lot of such tools, i personally recommend [markdownlint extension for VS Code](https://marketplace.visualstudio.com/items?itemName=DavidAnson.vscode-markdownlint), since i use VS Code.

## Creating Table of Contents

A table of contents allows reader to easily navigate through your document. You could manually create a table of content such as the one at the beginning of this document by doing the agonizing work of manually creating a list and linking each items to their respective headers, or you could use tools designed to do it for you. There's a command from [VS Code Markdown All in One extension](https://marketplace.visualstudio.com/items?itemName=yzhang.markdown-all-in-one) that you can use, or use online tools such as [Github Wiki TOC Generator](https://ecotrust-canada.github.io/markdown-toc/). The VS Code extention accepts `<!-- omit in toc -->` tag so that you can easily exclude a header from  the ToC.

Syntax:

```md
- [Usage](#usage)
- [Writing in Markdown](#writing-in-markdown)
  - [Hard-wrapped](#hard-wrapped)
  - [Special Characters](#special-characters)
- [Formattings](#formattings)
  - [Header](#header)
  - [Lists](#lists)
    - [Unordered Lists](#unordered-lists)
    - [Ordered Lists](#ordered-lists)
  - [Emphasis](#emphasis)
  - [Inline Code](#inline-code)
  - [Blockquotes](#blockquotes)
  - [Links](#links)
  - [Images](#images)
  - [Local Hyperlink](#local-hyperlink)
  - [Horizontal Rules](#horizontal-rules)
- [Github Flavored Markdown](#github-flavored-markdown)
  - [Strikethrough](#strikethrough)
  - [Syntax Highlighting](#syntax-highlighting)
  - [Task List](#task-list)
  - [Tables](#tables)
- [Converting Markdown](#converting-markdown)
- [Linting](#linting)
- [Creating Table of Contents](#creating-table-of-contents)
```
