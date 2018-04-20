[TOC]

#HTML Learning Notes

##HTML Elements 元素

### Terminology 中英文术语
- element 元素
- tag 标签
- content 内容

An HTML element usually consists of a `start tag` and `end tag`, with the `content` inserted in between:

`<tagname> Content </tagname>`

#### It can be nested

#### Do not forget the end tag
Or it might produce unexpected results

#### Empty HTML elements 
`<br>`

#### Use Lowercase Tags
W3C recommends lowercase in HTML

##HTML Attributes 属性

###Terminology
- attribute 属性

####Attributes
- All HTML elements can have attributes
- Attributes provide additional information about an element
- Attributes are always specified in **the start tag**
- Attributes usually come in name/value pairs like: **name="value"**

####Sample
- `herf` for `<a>` tag : `<a href="https://www.baidu.com">This is a link</a>`
- `src`/`width`/`height` for `<img>` tag : `<img src="img_girl.jpg" width="500" height="600">`


##HTML Headings 标题 

###Terminology
- Headings 标题
- Horizaotal Rules 水平线

- <h1> Hello h1 </h1>
- <h2> Hello h2 </h2>
- <h3> Hello h3 </h3>
- <h4> Hello h4 </h4>
- <h5> Hello h5 </h5>
- <h6> Hello h6 </h6>

####How to use headings
 Use HTML headings for headings only. Don't use headings to make text BIG or bold.
 
 Search engines use the headings to index the structure and content of your web pages. It is important to use headings to show the document structure.

####HTML Horizontal Rules
The `<hr>` element is used to separate content (or define a change) in an HTML page

####HTML `<head>` Element
- The HTML `<head>` element has nothing to do with HTML headings.
- The `<head>` element is a container for metadata. 
- The `<head>` element is placed between the `<html>` tag and the `<body>` tag

##HTML Paragraphs 段落

The HTML `<p>` element defines a paragraph

Browsers automatically add some white space (a margin) before and after a paragraph.

#### HTML Display
- You cannot be sure how HTML will be displayed.
- Large or small screens, and resized windows will create different results.
- With HTML, you cannot change the output by adding extra spaces or extra lines in your HTML code.
- The browser will remove any extra spaces and extra lines when the page is displayed

##HTML Styles 文本样式

###Style Chapter Summary
- Use the `style` attribute for styling HTML elements
- Use `background-color` for background color
- Use `color` for text colors
- Use `font-family` for text fonts
- Use `font-size` for text sizes
- Use `text-align` for text alignment

###Syntax
`<tagname style="property:value;">`

####HTML Background Color
The `background-color` property defines the background color for an HTML element.

`<body style="background-color:powderblue;">`

####HTML Text Color
The `color` property defines the text color for an HTML element.

`<h1 style="color:blue;">This is a heading</h1>`

####HTML Fonts
The `font-family` property defines the font to be used for an HTML element.

`<h1 style="font-family:verdana;">This is a heading</h1>`

####HTML Text Size
The `font-size` property defines the text size for an HTML element.

`<h1 style="font-size:300%;">This is a heading</h1>`

####HTML Text Alignment
The `text-align` property defines the horizontal text alignment for an HTML element

`<h1 style="text-align:center;">Centered Heading</h1>`

##HTML Formatting 文本格式
###Formatting Elements
- `<b>` - <b>Bold text</b>
- `<strong>` - <strong>Important text</strong>
- `<i>` - <i>Italic text</i>
- `<em>` - <em>Emphasized text</em>
- `<mark>` - <mark>Marked text</mark>
- `<small>` - <small>Small text</small>
- `<del>` - <del>Deleted text</del>
- `<ins>` - <ins>Inserted text</ins>
- `<sub>` - <sub>Subscript text</sub>
- `<sup>` - <sup>Superscript text</sup>

##HTML Quotations
- `<q>` - <q>Short Quotations</q>
- `<blockquote>` - <blockquote> Quotations <blockquote>
- `<abbr>` -Defines an abbreviation. <abbr title="xiaohuoji"> XHJ </abbr>
- `<address>` - Contact Information<address> Guangzhou <br> China </address>
- `<cite>` - defines the title of a work. <cite> Cite </cite> by xiaohuoji

##HTML Comments 注释
`<!-- Write your comments here -->`
<!-- Write your comments here -->

##HTML Colors 颜色
HTML colors are specified using predefined color names, or RGB, HEX, HSL, RGBA, HSLA values.

####Color Names
In HTML, a color can be specified by using a color name.

`Tomato` `Orange` `DodgerBlue` etc. 

HTML supports [140 standard color names](https://www.w3schools.com/colors/colors_names.asp)

####Background Color
`<h5 style="background-color:DodgerBlue;">Hello World</h5>`

<h5 style="background-color:DodgerBlue;">Hello World</h5>

####Text Color
`<h5 style="color:Tomato;">Hello World</h5>`

<h5 style="color:Tomato;">Hello World</h5>

####Border Color
`<h5 style="border:2px solid Tomato;">Hello World</h5>`

<h5 style="border:2px solid Tomato;">Hello World</h5>

####Color Values
`<h5 style="background-color:rgb(255, 99, 71);">...</h5>`

<h5 style="background-color:rgb(255, 99, 71);">...</h5>

####HEX Value
`<h5 style="background-color:#ff0000;">#ff0000</h5>`
<h5 style="background-color:#ff0000;">#ff0000</h5>

####HSL Value
`<h5 style="background-color:hsl(0, 100%, 50%);">hsl(0, 100%, 50%)</h5>`

<h5 style="background-color:hsl(0, 100%, 50%);">hsl(0, 100%, 50%)</h5>

##HTML CSS
CSS stands for Cascading Style Sheets.

CSS can be added to HTML elements in 3 ways:

- Inline - by using the style attribute in HTML elements
- Internal - by using a `<style>` element in the `<head>` section
- External - by using an external CSS file


####Part of CSS Syntax
- CSS Fonts - `<color>` `<font-family>` `<font-size>`
- CSS Border - `<border>`
- CSS Padding - `<padding>` defines a padding (space) between the text and the border
- CSS Margin- `<margin>` defines a margin (space) outside the border

##HTML Links

####Syntax
`<a href="url">link text</a>`

- Attribute `<a>`
- Property `href` : hypertext reference

####Hyperlinks
A link does not have to be text. It can be an image or any other HTML element.

####Local Links
The example above used an absolute URL (A full web address).

A local link (link to the same web site) is specified with a relative URL

####HTML Link Colors
define by using CSS
<style>
a:link {
    color: green;
    background-color: transparent;
    text-decoration: none;
}
a:visited {
    color: pink;
    background-color: transparent;
    text-decoration: none;
}
a:hover {
    color: red;
    background-color: transparent;
    text-decoration: underline;
}
a:active {
    color: yellow;
    background-color: transparent;
    text-decoration: underline;
}
</style>

<a href="https://www.baidu.com">Baidu</a>

##HTML Images

###Syntax
- `<img>` - tag - images
- `src` - Attribute - specifies the URL (web or local)
- `alt` - Attribute - provides an alternate text for an image
-  `width` - Attribute - iamge size
-  `height` - Attribute - iamge size 

`<img src="img_girl.jpg" alt="Girl in a jacket" width="500" height="600">`


**Note:**`<img>` tag can also use `style` attributes, and we suggest using the `style` attribute. It prevents styles sheets from changing the size of images

`<img src="/images/html5.gif" alt="HTML5 Icon" style="width:128px;height:128px;">`

####Image as a Link
To use an image as a link, put the `<img>` tag inside the `<a>` tag

####Image Maps
Use the `<map>` tag to define an image-map. An image-map is an image with clickable areas.

####Background Image
To add a background image on an HTML element, use the CSS property `background-image`

####The `<picture>` Element
To add more flexibility when specifying image resources.

The `<picture>` element contains a number of `<source>` elements

Each `<source>` element have attributes describing when their image is the most suitable.

The browser will use the first `<source>` element with matching attribute values, and ignore any following `<source>` elements.

##HTML Tables
- Use the HTML `<table>` element to define a table
- Use the HTML `<tr>` element to define a table row
- Use the HTML `<td>` element to define a table data
- Use the HTML `<th>` element to define a table heading
- Use the HTML `<caption>` element to define a table caption
- Use the CSS `border` property to define a border
- Use the CSS `border-collapse` property to collapse cell borders
- Use the CSS `padding` property to add padding to cells
- Use the CSS `text-align` property to align cell text
- Use the CSS `border-spacing` property to set the spacing between cells
- Use the `colspan` attribute to make a cell span many columns
- Use the `rowspan` attribute to make a cell span many rows
- Use the `id` attribute to uniquely define one table

##HTML Lists
- Use the HTML `<ul>` element to define an unordered list
- Use the CSS `list-style-type` property to define the list item marker
- Use the HTML `<ol>` element to define an ordered list
- Use the HTML `type` attribute to define the numbering type
- Use the HTML `<li>` element to define a list item
- Use the HTML `<dl>` element to define a description list
- Use the HTML `<dt>` element to define the description term
- Use the HTML `<dd>` element to describe the term in a description list
- Lists can be nested inside lists
- List items can contain other HTML elements
- Use the CSS property `float:left` or `display:inline` to display a list horizontally


##HTML BLocks
Every HTML element has a default display value depending on what type of element it is. The default display value for most elements is block or inline.


####Block-level Elements
`<div>` A block-level element always starts on a new line and takes up the full width available 

####Inline Elements
`<span>` An inline element does not start on a new line and only takes up as much width as necessary.


##HTML Classes
The `class` attribute specifies one or more class names for an HTML element.

The class name can be used by **CSS** and **JavaScript** to perform certain tasks for elements with the specified class name.

In CSS, to select elements with a specific class, write a period (.) character, followed by the name of the class

###Syntax
- specifies a class in HTML element `<tag class=city>` 
- Use in CSS`.city` 
- Use in JS `var x = document.getElementsByClassName("city");`

####Multiple Classes
An HTML element can have more than one classes name, each class name must be sperated by a space.

####Same Class, Different Tag
Different tags, can have the same class name and thereby share the same style.

But how about in JS ????

##HTML Id
The `id` attribute specifies a unique id for an HTML element (the value must be unique within the HTML document).

The id value can be used by CSS and JavaScript to perform certain tasks for a unique element with the specified id value.

In CSS, to select an element with a specific id, write a hash (#) character, followed by the id of the element

###Syntax
- The id value is case-sensitive.
- The id value must contain at least one character, and must not contain whitespace (spaces, tabs, etc.).
- specifies an id in HTML - `<tag id="myHeader">`
- Use In CSS - `#myHeader`
- Use In JS - `var x = document.getElementById("myHeader")`

####Bookmarks with ID and Links
HTML bookmarks are used to allow readers to jump to specific parts of a Web page.

Bookmarks can be useful if your webpage is very long.

To make a bookmark, you must first create the bookmark, and then add a link to it.

When the link is clicked, the page will scroll to the location with the bookmark.

create a bookmark - `<h2 id="C4">Chapter 4</h2>`

add a link to the book mark - `<a href="#C4">Jump to Chapter 4</a>`

##HTML Iframes
An iframe is used to display a web page within a web page.
###Syntax
- `src` attribute specifies the URL (web address) of the inline frame page.

##HTML JavaScript
JavaScript makes HTML pages more dynamic and interactive.

####The HTML `<script>` Tag
- The `<script>` tag is used to define a client-side script (JavaScript).
- The `<script>` element either contains scripting statements, or it points to an external script file through the `src` attribute.
- To select an HTML element, JavaScript very often use the `document.getElementById()` method.

####A Taste of JavaScript
- JavaScript can change HTML content
- JavaScript can change HTML styles
- JavaScript can change HTML attributes

####The HTML `<noscript>` Tag
The `<noscript>` tag is used to provide an alternate content for users that have disabled scripts in their browser or have a browser that doesn't support client-side scripts

##HTML File Paths

| Path	| Description | 
| --- | -------- |
|`<img src="picture.jpg">` |	picture.jpg is located in the same folder as the current page |
|`<img src="images/picture.jpg">` |	picture.jpg is located in the images folder in the current folder
|`<img src="/images/picture.jpg">	` | picture.jpg is located in the images folder at the root of the current web
|`<img src="../picture.jpg">` |	picture.jpg is located in the folder one level up from the current folder

File paths are used when linking to external files like:

- Web pages
- Images
- Style sheets
- JavaScripts

Paths type

- Absolute File Paths
- Relative File Paths


##HTML Head

The `<head>` element is a container for metadata (data about data) and is placed between the `<html>` tag and the `<body>` tag.

The following tags describe metadata:

- `<head>` -	Defines information about the document
- `<title>` -	 Defines the title of a document
- `<base>` -	Defines a default address or a default target for all links on a page
- `<link>` -	Defines the relationship between a document and an external resource
- `<meta>` -	Defines metadata about an HTML document
- `<script>` -	Defines a client-side script
- `<style>` -	Defines style information for a document

##HTML Layouts


###Syntax
- `<header>` - Defines a header for a document or a section
- `<nav>` - Defines a container for navigation links
- `<section>` - Defines a section in a document
- `<article>` - Defines an independent self-contained article
- `<aside>` - Defines content aside from the content (like a sidebar)
- `<footer>` - Defines a footer for a document or a section
- `<details>` - Defines additional details
- `<summary>` - Defines a heading for the <details> element


####HTML Layout Techniques
- HTML tables
- CSS float property
- CSS framework
- CSS flexbox

##HTML Responsive
Responsive Web Design makes your web page look good on all devices (desktops, tablets, and phones).

Responsive Web Design is about using HTML and CSS to resize, hide, shrink, enlarge, or move the content to make it look good on any screen

##HTML Computer Code
- `<code>` Defines programming code
- `<kbd>`	Defines keyboard input 
- `<samp>` Defines computer output
- `<var>`	Defines a variable
- `<pre>`	Defines preformatted text

##HTML Entities
Reserved characters in HTML must be replaced with character entities.

If you use the less than (<) or greater than (>) signs in your text, the browser might mix them with tags.

Character entities are used to display reserved characters in HTML.

To display a less than sign (<) we must write: `&lt`; or `&#60`;

[Check all in this](https://www.w3schools.com/html/html_entities.asp)

##HTML Symbols
Many mathematical, technical, and currency symbols, are not present on a normal keyboard.

To add such symbols to an HTML page, you can use an HTML entity name.

If no entity name exists, you can use an entity number, a decimal, or hexadecimal reference.

`<p>I will display &euro;</p>`
<p>I will display &euro;</p>

[Check all in this](https://www.w3schools.com/html/html_symbols.asp)

##HTML Charset
To display an HTML page correctly, a web browser must know which character set (character encoding) to use.

This is specified in the `<meta>` tag. See Above.

##HTML URL Encode
####URL - Uniform Resource Locator
A URL can be composed of words (w3schools.com), or an Internet Protocol (IP) address (192.68.20.50).

Web browsers request pages from web servers by using a URL.

Explanation:

- scheme - defines the type of Internet service (most common is http or https)
- prefix - defines a domain prefix (default for http is www)
- domain - defines the Internet domain name (like w3schools.com)
- port - defines the port number at the host (default for http is 80)
- path - defines a path at the server (If omitted: the root directory of the site)
- filename - defines the name of a document or resource
