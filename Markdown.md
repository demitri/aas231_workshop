# Markdown

## Motivation

**Why Markdown?** Markdown is used extensively in the software development community, but is commonly found outside of it as well. It’s simple to use and is beneficial for making plain text documents styled, easy to read, and encourages organization, with an extremely low barrier to adoption.

Dramatic curtain reveal: this document is written in plain text in Markdown.

## Markup Languages

As scientists, we appreciate the simplicity of plain text documents, but more importantly, their *longevity*: a text file created in the late 70s is exactly as readable now as it was back then (and undoubtedly will be in 50 years’ time). You would never put a Word document as a "readme" file in a directory of code, and even PDF is annoying if you are perusing files on the command line.

The down side to using plain text files is that they are... plain. They don't support things like formatted equations, tables, or clickable links. To get this functionality from plan text files, we use "markup" languages like HTML and LaTeX. The text content is decorated with codes that describe how it is to be displayed. For example,

```
<b><a href="http://apod.nasa.gov">APOD</a></b>
```

displays a web link in bold in HTML, and

```
$f(x) = \frac{1}{\sigma\sqrt{2\pi}}e^{-\frac{(x-\mu)^2}{2\sigma^2}}$
```

is LaTeX for

$f(x) = \frac{1}{\sigma\sqrt{2\pi}}e^{-\frac{(x-\mu)^2}{2\sigma^2}}$

The files are still plain text, but we exchange readability for this functionality (you don't open an HTML file in emacs to read it).

## Markdown

##### Introduction 

Markdown is a plain text markup language similar to HTML and LaTeX, but with the express design principle that the file remains completely readable as a plain text file with the markup. For example, if you were writing a plain text file and wanted to create a bullet list, you’d probably write:

```
 * dust cloud
 * phase-changing planets
 * alien megastructure
```

which is easy enough to read. However, when you open this file in a web page or text editor that is aware of Markdown, it will be rendered like this:

 * dust cloud
 * phase-changing planets
 * alien megastructure

OK, not the most breathtaking example. Markdown syntax supports also text styles like **bold**, *italics*, and _underlining_, which are written as:

```
**bold**, *italics*, and _underlining_
```

which are ways to emphasize text you might have written anyway.

##### Section Headers

Section headers are available in six sizes be writing `#` characters before the heading:

```
# Header 1
## Header 2
### Header 3
#### Header 4
##### Header 5
###### Header 6
```

becomes

# Header 1
## Header 2
### Header 3
#### Header 4
##### Header 5
###### Header 6

##### URLs

Bare web links can be specified by surround the link with `<>`, e.g. <http://apod.nasa.gov>. If you want a link to be clickable while not displaying the URL (i.e. like a web page), you can specify the title separately from the URL:

```
[APOD](http://apod.nasa.gov)
```

Thus, the word [APOD](http://apod.nasa.gov) in this sentence is clickable but the URL (which can be long and messy) is not displayed.

##### Tables

Tables are a very useful feature as well. They are created using plain text pipes `|` and dashes `-`, again, pretty much as you might do if you were writing a plain text file:

```
|   | header1 | header2 |
|---|---------|---------|
| 1 | red     | blue    |
| 2 | yellow  | green   |
```

This renders to:

|   | header1 | header2 |
|---|---------|---------|
| 1 | red     | blue    |
| 2 | yellow  | green   |

There are [online](https://www.tablesgenerator.com/markdown_tables) [tools](http://jakebathman.github.io/Markdown-Table-Generator/) that make creating tables easier.

##### Code

One of the most useful features of Markdown is the display of code blocks and code text. For example, in your "readme" you might say, "set the variable count to the number of items", but read as English that sentence is a little difficult to parse. By surrounding code words or literals with backticks, Markdown will render them in a monospaced font:

> set the variable `count` to the number of items

Whole code blocks can be defined by putting three backticks alone on a line above and below the block:

```
import astropy
print("Hello world.")
```

##### Equations

One of the nicest features for scientists is support for rendering LaTeX equations. Equations can be inline, e.g. $a^2 + b^2 = c^2$, by surrounding them with a single `$` or can be placed on their own line $$\sum_{i=0}{\frac{1}{m-1}}$$ by surrounding the LaTeX code with double `$$`. Note that the rendering will be slightly different between one `$`, e.g. $\sum_{i=0}{\frac{1}{m-1}}$, and the two above.

Not every sigle Markdown editor supports the display of equations, but most do. Sometimes you will need to enable the feature in a program’s preferences.

##### Images

Images can be placed inline. Note they are references – this is still a plain text file, after all. The image can be placed locally, for example, the image below is located in a folder in this directory. The format to place an image is similar to a URL, but with a leading `!`:

```
![Meerkat](images/Meerkat.jpg)
```

![Meerkat](images/Meerkat.jpg)

The part in the square brackets is the “alt-text”, the text you see when your mouse hovers over the picture. It is optional, but you still need the square brackets, e.g.

```
![](images/Meerkat.jpg)
```

Of course, why stop at images?

```
[![White and Nerdy](http://img.youtube.com/vi/N9qYF9DZPdw/0.jpg)](http://www.youtube.com/watch?v=N9qYF9DZPdw)
```

[![White and Nerdy](http://img.youtube.com/vi/N9qYF9DZPdw/0.jpg)](http://www.youtube.com/watch?v=N9qYF9DZPdw)


##### Horizontal Dividers

Sometimes you just need a horizontal divider. On a new line, just type one or more dashes:

```--```

to get this:

--

##### GitHub Flavored Markdown

It's worth noting that there are a few flavors of Markdown. Luckily there aren’t a glut of variations! The original Markdown syntax is widely supported of course. The one notable extension of this is GitHub Flavored Markdown. By far the most useful feature over the original specification is the ability to specify syntax highlighting in code blocks. If you are reading this on GitHub or in an editor that supports GitHub Flavored Markdown, this block (where the language is specified after the first three backticks):

```
    ```python
    import astropy
    for i in range(10):
    	print(i)
    ```
```

will appear with syntax highlighting as below:

```python
import astropy
for i in range(10):
	print(i)
```

You can also specify a code block on GitHub just by indenting the lines by four spaces:

    #!/usr/bin/env python
    import antigravity
    print("I can see my house from here!")

Other features include task lists:

 - [ ] memo to myself
 - [ ] do the dumb things I gotta do
 - [x] touch the puppet head

strikethrough text, or rather, ~~strikethrough text~~, and lots of emoji, where `:sunglasses:` turns into this: :sunglasses:. (Here is an [emoji cheat sheet](https://www.webpagefx.com/tools/emoji-cheat-sheet/).)

Note that some of these features will *only* be rendered while being viewed on [GitHub](https://github.com).

##### References & Cheat Sheets

Rather than go through the full specification here, we list several online references that describe the full Markdown feature set. As you can see, there's no possibility for syntax errors that prevent the page from being viewed (as you might encounter in LaTeX), and you can use as little or as much of the specification as you want.

 * [Original Markdown syntax](https://daringfireball.net/projects/markdown/syntax)
 * [GitHub flavored Markdown](https://guides.github.com/features/mastering-markdown/#GitHub-flavored-markdown)
 * [Markdown cheat sheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)
 *  [GitHub Markdown syntax](https://help.github.com/articles/basic-writing-and-formatting-syntax/)

## Why Markdown?

Why have we started with Markdown? Besides the benefit of writing documenation in a long-lasting format that can be rendered in a more display-friendly manner while being easily read in vi/emacs, Markdown has become ubiquitous. It is recognized and rendered automatically in GitHub, which makes for easier reading. There are many desktop and online editors that allow you to write documents in either the rendered mode directly or in plain text with the formatted result in a side-by-side window.

We recommend using Markdown when writing any stand-alone documentation text files and “readme” files. If in 50 years no one remembers what Markdown is, your files will have lost nothing and will be no less readable. By design.

## Recommended Markdown Editors

There are quite a few Markdown editors out there. Here are a few.

#### Mac Editors

 * [MacDown](https://macdown.uranusjr.com/) - split-pane view, perfect for learning Markdown
 * [Typora](https://typora.io/)
 * [Caret](https://caret.io)
 * [Bear](http://www.bear-writer.com/) - Markdown-compatible notes manager
 * [Quiver](http://happenapps.com) - another notes manager
 * (In fact it's a [little bit out of control](https://www.slant.co/topics/899/~best-markdown-editors-for-os-x).)

#### Windows Editors

 * [MarkdownPad](https://www.slant.co/topics/899/~best-markdown-editors-for-os-x)
 * [Typora](https://typora.io)
 * [ghostwriter](https://wereturtle.github.io/ghostwriter/)

#### Linux Editors
 
 * [Typora](https://typora.io)
 * [ghostwriter](https://wereturtle.github.io/ghostwriter/)
 
#### Browser-Based Editors

 * [Dillinger](https://dillinger.io)
 * [StackEdit](https://stackedit.io)
