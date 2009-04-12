Markup language zone naming policies
====================================
See the header of [programming language zone naming policies.markdown](./Programming%20language%20zones.markdown)
for some important notes.

Stylistic
---------
This section is for elements of markup that are purely presentational.

- `stylistic`
  - `stylistic.color`
  - `stylistic.typography`: `<font>this is different!</font>`
    - `stylistic.typography.weight...`: `*bold*, <b>bold</b>, [b]bold[/b]` (for elements that specifically change the weight of an element)
    - `stylistic.typography.variant...`: `^super^, <sup>super</sup>` (for elements that change which variant of a type family is used - superscript, subscript, italic, display, header, thin, etc)
      - `stylistic.typography.variant.slant...`: `_italic_, <i>italic</i>` (used to display italics and obliques)
    - `stylistic.typography.size...`: `<big>huge</big>, <small>tiny</small>` (used to change the point size of a typeface)

Structural
----------
These markup elements lend structure to the page, in a specifically semantic
(not just visual) way.

- `structural`
  - `structural.container...`
    - `structural.container.section...`: `<div>some stuff</div>` (any element referring to a section of a document)
    - `structural.container.paragraph`: `<p>Hi, I'm some text!</p>` (any element referring specifically to a paragraph of text)
  - `structural.header...`
    - `structural.header.title`: `<h1>a title</h1>, a title\n=======` (any title header)
    - `structural.header.section`: `<h2>a section</h2>, a section\n---------` (any section header)
    - `structural.header.tertiary...`: `<h3>Unimportant</h3>, <h5>Unimportant</h5>` (for any header that isn't a title nor a section header)
  - `structural.seperator...`: `<hr/>, --------`
  - `structural.connector...`: `<a href='http://google.com/'>Google</a>` (any connection between two documents or two locations in documents, internal or external)

Metadata
--------
Anything that affects the content of the document, but isn't an actual part of
the text of the document.

- `metadata`
  - `metadata.comment...`: `<!-- a comment -->`
    - `metadata.comment.line...`
    - `metadata.comment.block...`
    - `metadata.comment.documentation...`
  - `metadata.processing...`: anything, for instance, that would go in HTML's `<head>` block (things which are in the document, and change the processing of the document, but aren't actual text)
    - `metadata.processing.title`
