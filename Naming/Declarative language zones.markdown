Declarative language zone naming policies
=========================================
See the header of [programming language zone naming policies.markdown](./Programming%20language%20zones.markdown)
for some important notes.

This document is not the same as the other two. Declarative languages have no
inherent *semantic* meaning attached to their elements; thus, we can't achieve
our goal of hi-lighting elements in a semantic manner.

Instead, for the purposes of declarative languages, we will name (and thus
hilight) elements based on their syntax, not their semantic purpose. While
this is not ideal, it's better than having a non-hi-lighted document.

Element
-------
Most things in a declarative language are "elements" - in some languages,
these might be called "tags" or "keys" (as opposed to "content" or "values").

- `element...`: `<element/>` from XML, `:element:` from YAML
   - `element.paired`: `<element></element>` from XML
   - `element.standalone`: `<element/>` from XML

Attribute
---------
In some declarative languages, the meaning/content/purpose of an `element` can
be modified by the addition of "attributes".

- `attribute...`: `foo="bar"` in `<element foo="bar">` from SGML
   - `attribute.boolean`: `attribute` in `<element attribute>` from SGML (any attribute that doesn't contain its own content)

Metadata
--------
Anything that affects the content of the document, but isn't an actual part of
the text of the document.

- `metadata`
  - `metadata.comment...`: `<!-- a comment -->`
    - `metadata.comment.line...`
    - `metadata.comment.block...`
    - `metadata.comment.documentation...`
  - `metadata.processing...`: (things which are in the document, and change the processing of the document, but aren't actual text)
    - `metadata.processing.version` `<!DOCTYPE HTML>`, `%YAML 1.2\n---` (declarations that describe the content type, and possible specific version of the content type, of the document)

Delimiters
----------
Delimiters are things that, well, delimit. They mark the edges of things,
where one thing becomes another, or where two things become one.

- `delimiter`
  - `delimiter.balanced...`
    - `delimiter.balanced.quote...`: `'...', "..."` in XML's attributes, denoting a quoted string of some sort
    - `delimiter.balanced.bracket...`: `<...>` in XML, denoting a contained bit of something
  - `delimiter.separator...`
    - `delimiter.separator.namespace...`: `:` in XML's tag names
    - `delimiter.separator.pairing...`
      - `delimiter.separator.pairing.content-value`: `:` in YAML
      - `delimiter.separator.pairing.attribute-value`: `=` in XML's attribute definitions
  - `delimiter.terminator`: `;` in most languages
