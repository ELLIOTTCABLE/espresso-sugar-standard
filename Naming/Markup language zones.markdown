Markup language zone naming policies
====================================
See the header of [programming language zone naming policies.markdown](Programming language zones.markdown)
for some important notes.

Stylistic
---------
This section is for elements of markup that are purely presentational.

- <b>stylistic</b>
  - <b>stylistic.color</b>
  - <b>stylistic.typography:</b> `<font>this is different!</font>`
    - <b>stylistic.typography.weight...:</b> `*bold*`, `<b>bold</b>`, `[b]bold[/b]` _(for elements that specifically change the weight of an element)_
    - <b>stylistic.typography.variant...:</b> `^super^`, `<sup>super</sup>` _(for elements that change which variant of a type family is used - superscript, subscript, italic, display, header, thin, etc)_
      - <b>stylistic.typography.variant.slant...:</b> `_italic_`, `<i>italic</i>` _(used to display italics and obliques)_
    - <b>stylistic.typography.size...:</b> `<big>huge</big>`, `<small>tiny</small>` _(used to change the point size of a typeface)_

Structural
----------
These markup elements lend structure to the page, in a specifically semantic
(not just visual) way.

- <b>structural</b>
  - <b>structural.vessel...</b>
    - <b>structural.vessel.section...:</b> `<div>some stuff</div>` _(any element referring to a section of a document)_
    - <b>structural.vessel.paragraph:</b> `<p>Hi, I'm some text!</p>` _(any element referring specifically to a paragraph of text)_
  - <b>structural.header...</b>
    - <b>structural.header.title:</b> `<h1>a title</h1>`, `a title\n=======` _(any title header)_
    - <b>structural.header.section:</b> `<h2>a section</h2>`, `a section\n---------` _(any section header)_
    - <b>structural.header.tertiary...:</b> `<h3>Unimportent</h3>`, `<h5>Unimportent</h5>` _(for any header that isn't a title nor a section header)_
  - <b>structural.seperator...:</b> `<hr/>`, `--------`

Miscellaneous
-------------
Other stuff. This needs a better name. **Unfinished!**

- <b>miscellaneous</b>
  - <b>miscellaneous.connection.*:</b> `<a href='http://google.com/'>Google</a>` _(any connection to something else, internal or external)_

Metadata
--------
Anything that affects the content of the document, but isn't an actual part of
the text of the document. Think HTML's `<head>` element's contents. **Unfinished!**

- <b>metadata...</b>
