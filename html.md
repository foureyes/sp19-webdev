---
layout: slides
title: HTML
---

<section markdown="block" class="intro-slide">
# HTML 

### Give your page structure and meaning with HTML!

</section>


<section markdown="block">
## HTML

__HTML__ is the language that describes the __structure__ and __semantic content__ of a document on the web; it consists of:

* __content__ (just plain text) 📖
* and __elements__ (tags) that give structure to the text 🔨

</section>

<section markdown="block" data-background="#440000">
# HTML is for content and structure

</section>

<section markdown="block">
<h2> <strong>H</strong>yper-<Strong>T</strong>ext <strong>M</strong>arkup <strong>L</strong>anguage. </h2>

<span class="fragment"><strong>Hyper-Text</strong> &rarr;</span><span class="fragment">Because it allows you to link to other documents on the web! 🌎 </span>

__What about the markup part?__ &rarr;
{:.fragment}

* {:.fragment} markup is a method of __annotating__ text...
	* {:.fragment} markup itself is syntactically distinguishable from content
	* {:.fragment} markup is applied to text by using _tags_
* {:.fragment} HTML is generally not considered a language in the _programming_ language sense

</section>

<section markdown="block">
## Elements and Tags

An __element__ a single part of an HTML document; it encompasses both structure and (optionally) content: a paragraph, navigation, etc.

* {:.fragment} an __element__ is made up of __tags__ and, optionally, text: <code>&lt;p&gt;Some Content&lt;/p&gt;</code>
* {:.fragment} __tags__ are used to mark the start and end of an HTML element: <code>&lt;p&gt; ... &lt;/p&gt;</code>
* {:.fragment} an __opening tag__ is an element's name surrounded by angle brackets: <code>&lt;p&gt;</code>
* {:.fragment} an __closing tag__ is an element's name prefixed with a forward slash and surrounded by angle brackets: <code>&lt;/p&gt;</code>
</section>

<section markdown="block">
## Tags Continued

There are a few ways that __tags__ and __content__ can be combined to create __elements__.  &rarr;

* {:.fragment} an open and close tag surrounding content: <code>&lt;h1&gt;So Flawless&lt;/h1&gt;</code>
* {:.fragment} an open and close tag without content: <code>&lt;script src="iamhackr.js"&gt;&lt;script&gt;</code>
* {:.fragment} only an open tag <code>&lt;img src="puppies.png"&gt;</code>

</section>

<section markdown="block">
## Attributes

### An __opening tag__ can contain __attributes__ 


* {:.fragment} an __attribute__ is part of a tag that provides additional information about an element
* {:.fragment} it's composed of a name/value pair joined by an equal sign
* {:.fragment} it's is placed after the name of the element in a tag, but before the last angle bracket: <code>&lt;img src="puppies.png"&gt;</code>
* {:.fragment} the value doesn't have to be quoted, but it's good practice to do so... to avoid issues like this:<code>&lt;input type=text value=what is this&gt;</code>
</section>

<section markdown="block">
## A Quick Diagram

__Name the parts of this markup__ &rarr;

<pre><code data-trim contenteditable>&lt;a href="http://we.love.pizza&gt;pizza!&lt;/a&gt;
</code></pre>

<pre><code data-trim contenteditable>                element
                    |
     +--------------+---------------------+
     |                                    | 
    &lt;a href="http://we.love.pizza"&gt;pizza!&lt;/a&gt;
     |      |                             |
     |      attribute                     |
start tag                            end tag
</code></pre>
{:.fragment}
</section>

<section markdown="block">
## Special Characters

### Some Characters Have Meaning in HTML

(for example: &lt;, &gt;, &amp;) 
{:.fragment}

If you need these characters in your content, Use an __HTML entity__, a sequence of characters that represents these special characters
{:.fragment}

* {:.fragment} HTML entities start with __&__, followed by a __name__, and end with __;__
* {:.fragment} for example, <code>&amp;lt;</code> is <code>&lt;</code> and <code>&amp;amp;</code> is an <code>&amp;</code>
* {:.fragment} a [list of HTML entities](http://dev.w3.org/html5/html-author/charref)
</section>

<section markdown="block">
## Some Commonly Used HTML Entities:

<pre><code data-trim contenteditable>&amp;amp; ... ampersand (&amp;)
&amp;nbsp; ... non breaking space (&nbsp;)
&amp;lt; ... less than (&lt;)
&amp;gt; ... greater than (&gt;)
&amp;quot; ... double quotes (&quot;)
&amp;apos; ... single quote (&apos;)
</code></pre>
</section>

<section markdown="block">
## HTML Specifications

Two groups, __WHATWG__ and __W3C__, work together to specify HTML 🖋️

* {:.fragment} <strong>W</strong>eb <strong>H</strong>ypertext <strong>A</strong>pplication <strong>T</strong>echnology <strong>W</strong>orking <strong>G</strong>roup has a [living HTML standard](https://html.spec.whatwg.org/multipage/)
	* {:.fragment} continuously evolving standard
	* {:.fragment} no version numbers
	* {:.fragment} _community_ driven
* {:.fragment} <strong>W</strong>orld <strong>W</strong>ide <strong>W</strong>eb <strong>C</strong>onsortium) is basing the most recent versions of HTML on WHATWG's living standard
	* {:.fragment} it snapshots versions 
	* {:.fragment} the [latest version is HTML5](https://wiki.whatwg.org/wiki/FAQ#Is_participation_free.3F)
	* {:.fragment} version releases are a bit slower than WHATWG's
</section>

<section markdown="block">
## HTML5, doctype 

__HTML5__ is the most current version of HTML. It defines a bunch of things:

* {:.fragment} _actual_ __markup__ (like we've seen already) ✔️
* {:.fragment} __scripting APIs__ (through JavaScript) ✔️

To indicate that your page uses HTML5, use the following __doctype declaration__ at the top of your page:
{:.fragment}

<pre><code data-trim contenteditable>&lt;!doctype html&gt;
</code></pre>
{:.fragment}

This doctype will let browsers know how to _render_ your page.
{:.fragment}
</section>

<section markdown="block">
## Dealing with Bad Markup

Browsers are pretty __forgiving__ when it comes to <strong><em>bad</em> markup</strong>: 😅

<pre><code data-trim contenteditable>No tags surrounding me!
</code></pre>
{:.fragment}

<code>html</code>, <code>head</code>, and <code>body</code> tags are inserted
{:.fragment}

<pre><code data-trim contenteditable>&lt;html&gt;
&lt;body&gt;
		Where's my close body?
&lt;/html&gt;
</code></pre>
{:.fragment}

<code>body</code> is automatically closed
{:.fragment}

</section>

<section markdown="block">
## And Now, Some Elements

### Finally... a quick tour of some elements you'll be using

(check out [mdn's html elements reference for more detail!](https://developer.mozilla.org/en-US/docs/Web/HTML/Element)

</section>
<section markdown="block">
## Root, Meta Data and Content Elements

__&lt;!doctype html&gt;__: informs the browser to use the appropriate rendering mode for this version of html
{:.fragment}

__&lt;html&gt;&lt;/html&gt;__: the _root_ or top-level element of a document.
{:.fragment}

__&lt;head&gt;&lt;/head&gt;__: contains meta data _about_ the document, like which css file(s) to use (_link_), the _title_ of the document (shown in the tab), etc.
{:.fragment}

__&lt;body&gt;&lt;/body&gt;__: the content of the document; only one body per document
{:.fragment}

</section>

<section markdown="block">
## That Meta Data...

### Within the Head Element

__&lt;link href="name-of-file.css" rel="stylesheet"&gt;__: bring in a stylesheet
{:.fragment}

__&lt;title&gt;&lt;/title&gt;__: title of the page
{:.fragment}


</section>

<section markdown="block">
## Headers, Footers and Navigation

__&lt;header&gt;&lt;/header&gt;__: represents introductory content such as navigation, logo, search form etc.
{:.fragment}

__&lt;footer&gt;&lt;/footer&gt;__: typically contains content such as copyright information, author, etc.
{:.fragment} 

__&lt;h1&gt;&lt;/h1&gt; (through &lt;h6&gt;)__: section headers with 1 being the highest and 6 being the lowest
{:.fragment}

__&lt;nav&gt;&lt;/nav&gt;__: describes a part of the page that provides navigation (there can be more than one nav element)
{:.fragment}

</section>

<section markdown="block">
## Breaking Up Your Actual Content

__&lt;article&gt;&lt;/article&gt;__: self-contained composition, possibly independently distributable (blog or forum post, magazine article, a user's comment, etc.)
{:.fragment}

__&lt;section&gt;&lt;/section&gt;__: generic _section_ of your page (thematic grouping of content, usually with heading), like chapters in a book, broad sections of page (overview, news, contact)
{:.fragment}

__&lt;img src="/path/to/image.jpg" alt="describes image"&gt;__: an image, no closing tag
{:.fragment}

__&lt;br&gt;__: line break (no closing tag)
{:.fragment}

__&lt;hr&gt;__: horizontal line (no closing tag)
{:.fragment}
</section>

<section markdown="block">
## Blocks

For organizing blocks / sections of content within body...

__&lt;p&gt;&lt;/p&gt;__: pargraph
{:.fragment} 

__&lt;blockquote&gt;&lt;/blockquote&gt;__: extended quotation 
{:.fragment}

__&lt;ul&gt;&lt;/ul&gt;, &lt;ol&gt;&lt;/ol&gt; and nested &lt;li&gt;&lt;/li&gt;__: unordered and ordered list with nested list items
{:.fragment}

__&lt;div&gt;&lt;/div&gt;__: _generic_ block element 
{:.fragment}

__&lt;table&gt;&lt;/table&gt; (along with thead, tbody, tr, td)__: tabular data
{:.fragment}

</section>

<section markdown="block">
## Inline

For annotating a word or line...

__&lt;a href="/path/to/page.html"&gt;&lt;/a&gt;__: link to another page or section within this page
{:.fragment} 

__&lt;strong&gt;&lt;/strong&gt;__: element has strong importance / urgency within context of document
{:.fragment}

__&lt;span&gt;&lt;/span&gt;__: generic inline element
{:.fragment}

</section>


