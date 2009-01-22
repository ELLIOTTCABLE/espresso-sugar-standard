Programming language zone naming policies
=========================================
This document's purpose is to regulate the 'naming' of [syntax 'zones'][] in
[Espresso][] [Sugars][]. Each 'zone' in an Espresso Sugar has it's own,
unique, identifier. This identifier is composed of 'classes', separated by
periods.

Themes written for Espresso can then attach syntax highlighting instructions
to zones by 'selecting' them with CSS selectors. Selectors can be applied to
any combination of the classes used in zone identifiers. We are attempting to
regulate the basic categories of classes, so that most themes written for
Espresso will 'work' with as many Sugars as possible — that is, it will
correctly highlight syntax 'zones' as intended by the theme author.

### Sugar Authors
If you're going to apply this standard to your sugars, *please* either follow
all of it or none of it. The entire purpose of this document will be
invalidated if you pick and choose which classes you like and which you don't.

Also, avoid utilizing ad-hoc class names in this tree — for instance, if your
language has a syntactical construct called a 'tuple', don't frivolously give
the zone an identifier of "literal.collection.tuple", as that doesn't
currently exist in the specification. If another Sugar author also needs a
tuple, they might instead decide to identify it as "literal.tuple" — then a
themer has to make their theme use both of those informal categories to
highlight tuples in all languages.

Certain categories *do* allow extension, these categories' names end with a
'...' in the spec. You're free to add language-specific extensions to the end
of these identifiers; due to the nature of Espresso's selector system, themes
will still correctly target your elements as long as you have all of the
classes from the spec in your identifier. In the above example, you could
instead identify your 'tuple' element with an extension to the
"literal.collection.set" category (which allows extension, as you can see
below), such as "literal.collection.set.tuple".

If you believe that an element of syntax from the programming language that
you are writing a Sugar for simply does not fit in any existing category on
this tree, nor do you believe is it a variation upon one of the extensible
categories, you may add a temporary class with an `x-` prefix to indicate that
you expect that category to be added in the near future. For instance, in the
above example, if you really didn't believe that a 'tuple' was anything like
a "literal.collection.set" as defined by this document, you could utilize an
identifier of "literal.collection.x-tuple". This indicates to themers
(see below) that they shouldn't theme this class until it is accepted into
the spec.

If you would like to see classes added to this spec, feel free to contact me
(elliottcable) with a request. I'm quite happy to see this spec expanded to
support as many languages as possible, but I do not want to add any classes
that can map cleanly to an existing class, as that induces confusion.

### Themers
If you're writing a theme, and want to support Sugars that use this spec, you
needn't actually look at the Sugar's source code. If it truly follows this
spec, you need only add CSS selectors for each of the below class trees, and
style them as you desire.

If you read the section above (intended for Sugar Authors), you'll probably
realize that you should **not** style any class in any Sugar when the class
starts with `x-`. This ensures your theme will work with as many sugars as
possible.

Specification
=============

Literals
--------
A literal is an element that is directly typed into the source code. In
some languages, these might be called constants - however, I consider that too
ambiguous, as most languages which Espresso users will often come across, a
constant means something else entirely (see `keyword.constant`).

- `literal...`
  - `literal.string...`: `"hello world"`
  - `literal.regex...`: `/^([\w]+).*$/`
  - `literal.numeric`
    - `literal.numeric.integer`
      - `literal.numeric.integer.binary...`: `0b1, 0b101010`, and in some languages `-0b1000`
      - `literal.numeric.integer.decimal...`: `1, 42`, and in some languages `-8`
      - `literal.numeric.integer.octal...`: `01, 052`, and in some languages `-010`
      - `literal.numeric.integer.hex...`: `0x1, 0x2A`, and in some languages `-0x8`
    - `literal.numeric.float...`: `1.0, 4.2`, and in some languages `-8.8`
    - `literal.numeric.exponent...`: `e1, e42` (should identify the exponential part of the literal, not the entire literal)
  - `literal.collection`
    - `literal.collection.set...`: (I don't actually know of any language that has a literal construct for a set, but if one does, it would go here)
    - `literal.collection.array...`: `[1, 2, 3]`
    - `literal.collection.dictionary...`: `Hash` in Ruby, `dict` in Python, `array()` in PHP
  - `literal.keyword`: (any value that acts as a keyword but returns a single, known value)
    - `literal.keyword.bool...`: `true, false`
    - `literal.keyword.nothing...`: `nil, NULL, undefined, NaN`
  - `literal.escape...`: `\e, \{, \!`
    - `literal.escape.linebreak` `\n, \r\n, \x0D\x0A, PHP_EOL`
    - `literal.escape.tab` `\t`

Identifiers
-----------
An identifier is a syntatical element that uniquely identifies one object of
some sort in the language. This isn't restricted to the Object-Oriented
Language definition of 'object', this also means anything in a language which
can be referenced in some way.

- `identifier`
  - `identifier.function`: `func(1, 2, 3)` _(referring to a identifier that points to a specific function - such as a function/method call)_
  - `identifier.type`: `NSString`, `HTTP`, `Fixnum`, `double` _(an umbrella for 'prototypes', 'classes', 'types', and any other language feature that serves a similar purpose)_
  - `identifier.variable...`
    - `identifier.variable.constant...`: `Var`, `VAR`
    - `identifier.variable.global...`: `$var` in Ruby, `$_VAR` in PHP
    - `identifier.variable.instance...`: `@var`, `@@var`
    - `identifier.variable.local...`: `var`
    - `identifier.variable.parameter...`: `var` in the context of a method definition

Keywords
--------
A keyword is an element defined in the language's definition itself - it can't
be changed by the programmer, and it usually invokes or references something
hardcoded into the language's compiler/parser/interpreter.

- `keyword`
  - `keyword.control`: (used for loops, conditionals and general flow control)
    - `keyword.control.exception...`: `raise, rescue, ensure, throw, catch` (used to manage exceptions)
    - `keyword.control.flow...`: `while, for, break, goto, if`/`then`/`else, begin...end` (changes the 'direction' of / current location in the executing code)
  - `keyword.modifier...`: (used for tacking onto declarations)
    - `keyword.modifier.scope...`: `public, protected, private` (changes the 'scope' of a particular declaration)
  - `keyword.definition...`: `class, function, method, module, lambda` (used for creating or modifying a container)

Containers
----------
These are less being defined for the purpose of highlighting, and more for use
in attaching Itemizers, and for the purpose of the subzones. Any syntactical
construct that is meant to seperate out a piece of code from other code, goes
here.

- `container`:
  - `container.class...`
  - `container.function...`
  - `container.block...`: `lambda {}` in Ruby, anonymous function in JavaScript, closures in many other languages (any block of code that acts as exactly that, a block of code)

Metadata
--------
This is mostly for comments - I can't think of anything else to go under this
heading, but there may be such things.

- `metadata...`: (for information that will be ignored by the compiler/interpreter, or has semantic meaning beyond that involved in it's normal execution)
  - `metadata.type-signature`: `map :: (a -> b) -> [a] -> [b]` from Haskell
  - `metadata.comment`
    - `metadata.comment.line...`
    - `metadata.comment.block...`
    - `metadata.comment.documentation...`: RDoc/YARD, JavaDoc, phpDocumentor comments (comments formulated in a way accepted by the community and documentation-generating-tools to be documentation-blocks)
  - `metadata.processing...`: `#define, #ifdef` (anything that changes the way code is compiled/interpreted, but isn't code itself)
    - `metadata.processing.comment...` `# -*-mode: tcl; fill-column: 75; tab-width: 8; coding: iso-latin-1-unix -*- ` in emacs or `# encoding: utf-8` in Ruby (other sorts of magic comments that affect the code)
      - `metadata.processing.comment.shebang`: `#!/usr/bin/env ruby -Ku` (UNIX shell scripting shebangs)

Operators
---------
The difference between operators and keywords bears some discussing. Operators
are almost always punctuation, whereas keywords are almost always textual.
There are exceptions to this rule (`and` and `or` are operators, because
they're simply alternatives to `&&` and `||`), but it's a good generalization.

- `operator`
  - `operator.comparator...`: `<, >, <=, >=, ==, ===`
  - `operator.accessor...`: `=, +=, -=, *=, ||=`, as well as `*var` and `&var` from C (for getters/setters/assignments)
  - `operator.mathematical...`: `+, -, *, /, %`
  - `operator.logical...`: `!!, &&, ||, ^, !, &, |`

Delimiters
----------
Delimiters are things that, well, delimit. They mark the edges of things,
where one thing becomes another, or where two things become one.

- `delimiter`
  - `delimiter.balanced...`
    - `delimiter.balanced.quote`
      - `delimiter.quote.balanced.double`: `"these"`
      - `delimiter.quote.balanced.single`: `'these'`
      - `delimiter.quote.balanced.backtick`: `` `these` ``
    - `delimiter.balanced.parenthesis`: `(these)`
    - `delimiter.balanced.square-brace`: `[these]`
    - `delimiter.balanced.curly-brace`: `{these}`
  - `delimiter.seperator...`
    - `delimiter.seperator.namespace...`: `::` in ruby
    - `delimiter.seperator.comma`: `,`
    - `delimiter.seperator.pairing...`: `=>` in Ruby, ':' in JavaScript
  - `delimiter.terminator`
