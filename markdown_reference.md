This readme file is a reference resource for common markdown elements that could be integrated for files in Jupyter notebooks, Github repositories, and common LaTeX document structures.

<a href='#top_of_page' id='top_of_page' class='anchor' aria-hidden='true'>Top of Page</a>

---
**Headers**

A common structure to organize documents includes headers.  Headers can range from 1 to 6 levels of sizing with hashtags.

# This is the largest possible header using `1#`
## This is the second largest possible header using `2#'s`
###### This is the smallest possible header using `6#'s`
---
[Here is a link on the same page](#bottom_of_page)

---
**Bold Elements**

Using the `**` syntax, you can format your text with the bold/strong emphasis element:
> **Here is bold text by using `**` before and after.**
---
**Italic Elements**

Using the `*` syntax, you can format your text with the italic emphasis element:
> *This line of text is italicized text by using `*` before and after the text.*
---
**Color for your text**

Markdown does not support color.  However, HTML does.  Additionally, Github strips out certain HTML elements for security purposes, and therefore does not support color elements.  For Jupyter Files, Markdown does support color when displayed in .ipynb files, and you can consider to add in color elements:
> `<span style="color:blue"> This text is blue, using HTML elements </span>`
---
**Code Blocks**

You can establish a code block with the tilted apostrophe symbols, above the tab key on your keyboard: 
> `Here is an example of a code block`
---
**Quote Blocks**

You can indent your paragraphs or specific quotes using the `>` operator:
> This is an indented quote block for formatting text. 
---
**External URLs**

You can set external URLs with the `[Text to describe URL](URL website goes here)`
> [Here is a URL that is hyperlinked](www.google.com)
---
<!--**Internal URLs**-
--- -->
**Bullet Points**

You can define a bullet point either with the - or the * symbols, spaced out from the text.
> - This is the first bullet point in this sequence.
> - Here is the second bullet point in the sequence.

As an alternative, you can create lists within lists, or nested bullet points.

* Here is our first bullet point in the second list. 
  * After typing **2 spaces** before this second bullet point, we have created a nested list.
    * This process can continue on several layers, if you so choose.
  
---
**Emojis (the new emoticon)**

Emojis display emoticons (text-based images), in a graphical display, as found in messaging softwares both in Enterprise and consumer solutions.

_Some examples follow:_
`:bar_chart:` :bar_chart:
`:thumbsup:` :thumbsup:
`:books:` :books:
`:smile:` :smile:
`:sweat:` :sweat:
`:smiling_imp:` :smiling_imp:

You can view a comprehensive list on the [emoji cheatsheet](https://www.webpagefx.com/tools/emoji-cheat-sheet/).

---
 ### Data dictionary goes below
 | Column 1 | Column 2 | Column 3 |
 |----------|----------|----------|
 |variable | definition | qualities|
 
| Column | Type of Data | Examples of data |
|--------|---------------|-------------------|
|Gender | categorical | Male or Female |
| Height | numerical |  range of 5" to 6'5" | 
| BMI | ordinal | 20 to 35 |
 
 ---
 Horizontal line above
 
 ### Image going below
 ![This is a panda](https://steamuserimages-a.akamaihd.net/ugc/909030790735843820/C68D6FF722AE9F7BCF614E0B5B9ABA0EA11322E5/)
 
### Here is a dropdown 
 <details>
  <summary><strong>Dropdown below :bar_chart:</strong></summary>

#### Here is text
#### More text
<br>
Regular text
Ending the dropdown
</details>

---
### Support is included for special characters
These can be written as &#8721; `&#8721;` using [XML and HTML elements](https://en.wikipedia.org/wiki/List_of_XML_and_HTML_character_entity_references). 

<!--Internal hyperlinks <h1 class="title">
        True Happiness
    </h1>
    <div id="TOC">
        <ul>
            <li>
                <a href="#introduction">Introduction</a>
            </li>
            <li>
                <a href="#first-attempts">First Attempts</a>
            </li>
        </ul>
    </div>
    <div id="introduction">
        <h2>
            <a href="#TOC">Introduction</a>
        </h2>
        <p>
            Many have posed the question of true happiness. In this blog post we propose to solve it.
        </p>
    </div>
    <div id="first-attempts">
        <h2>
            <a href="#TOC">First Attempts</a>
        </h2>
        <p>
            The earliest attempts at attaining true happiness of course aimed at pleasure. Soon, though, the downside of pleasure was revealed.
        </p>
    </div> End Internal hyperlinks -->

# Bottom_of_page

[Top of page](#top_of_page)

## Licenses
License

[![CC-4.0-by-nc-nd](https://licensebuttons.net/l/by-nc-nd/3.0/88x31.png)](https://creativecommons.org/licenses/by-nc-nd/4.0/)

To the extent possible under law, [David Yakobovitch](http://davidyakobovitch.com/) has licensed this work under Creative Commons, 4.0-NC-ND.  This [license](https://creativecommons.org/licenses/by-nc-nd/4.0/) is the most restrictive of Creative Commons six main licenses, only allowing others to download your works and share them with others as long as they credit the author, but they can’t change them in any way or use them commercially.

