# Literals
A literal is an element that is directly typed into the source code. In
some languages, these might be called constants - however, I consider that too
ambiguous, as most languages which Espresso users will often come across, a
constant means something else entirely (see `keyword.constant`).

- <b>literal.*</b>
  - <b>literal.string.*:</b> `"hello world"`
  - <b>literal.regex.*:</b> `/^([\w]+).*$/`
  - <b>literal.numeric.*:</b> `1 22 35.124 1.54e9`
  - <b>literal.enumerable.*</b>
    - <b>literal.enumerable.set.*</b>
    - <b>literal.enumerable.array.*:</b> `[1, 2, 3]`
    - <b>literal.enumerable.dictionary.*::</b> `Hash` in Ruby, `dict` in Python, `array()` in PHP

# Identifiers
An identifier is a syntatical element that uniquely identifies one object of
some sort in the language. This isn't restricted to the Object-Oriented
Language definition of 'object', this also means anything in a language which
can be referenced in some way.

- - <b>identifier.*</b> 
  - <b>identifier.function.*:</b> `func(1, 2, 3)` _(referring to a identifier that points to a specific function - such as a function/method call)_
    - <b>identifier.function.support.*:</b> `malloc()` and `printf()` in C, `strstr()` and `array()` in PHP _(built-in functions)_
  - <b>identifier.variable.*</b>
    - <b>identifier.variable.constant.*:</b> `Var`, `VAR`
    - <b>identifier.variable.global.*:</b> `$var` in Ruby, `$_VAR` in PHP

# Keywords
A keyword is an element defined in the language's definition itself - it can't
be changed by the programmer, and it usually invokes or references something
hardcoded into the language's compiler/parser/interpreter.

- - <b>keyword.*</b>
  - <b>keyword.control.*:</b> _(used for loops, conditionals and general flow control)_
    - <b>keyword.control.exception.*:</b> `raise`, `rescue`, `ensure`, `throw`, `catch` _(used to manage exceptions)_
    - <b>keyword.control.flow.*:</b> `while`, `for`, `break`, `goto`, `if`/`then`/`else` _(changes the 'direction' of / current location in the executing code)_
  - <b>keyword.modifier.*:</b> `abstract`, `public`, `private` _(used for tacking onto declarations)_
    - <b>keyword.modifier.scope.*:</b> `public`, `protected`, `private` _(changes the 'scope' of a particular declaration)_
  - <b>keyword.definition.*:</b> `class`, `function`, `method`, `module`, `begin`, `lambda` _(used for creating or modifying a <b>block.*</b> element)_
  - <b>keyword.type.*</b>
  - <b>keyword.literal.*</b>
    - <b>keyword.literal.constant.*:</b> `nil`, `true`, `false`, `undefined`, `NaN`, `NULL` _(any value that acts as a literal for a value that doesn't change under any circumstances)_

# Blocks
These are less being defined for the purpose of highlighting, and more for use
in attaching Itemizers, and for the purpose of the subzones. Anything that is
a block of code should go here.

- - <b>block.*:</b> _(used for anything that attaches a block of code to something, such as a definition, iterator, or closure)_
  - <b>block.typedef.*</b>
    - <b>block.typedef.class.*</b>
    - <b>block.typedef.module.*</b>
    - <b>block.typedef.prototype.*</b>
  - <b>block.function.*</b>
  - <b>block.iterator.*</b>
  - <b>block.closure.*:</b> `lambda {}` in Ruby, anonymous function in JavaScript _(any block of code that acts as exactly that, a block of code packaged into a variable)_

# Metadata
This is mostly for comments - I can't think of anything else to go under this
heading, but there may be such things.

- - <b>metadata.*:</b> _(for information that will be ignored by the compiler/interpreter, or has semantic meaning beyond that involved in it's normal execution)_
  - <b>metadata.comment.*</b>
    - <b>metadata.comment.line.*</b>
    - <b>metadata.comment.block.*</b>
    - <b>metadata.comment.documentation.*:</b> RDoc/YARD, JavaDoc, phpDocumentor comments _(comments formulated in a way accepted by the community and documentation-generating-tools to be documentation-blocks)_
      - <b>metadata.comment.documentation.tag.*:</b> `@name`, `@description` _(tags of which the widly-accepted documentation-generators are aware, which control the generated documentation)_
  - <b>metadata.processing.*:</b> _(anything that changes the way code is compiled/interpreted, but isn't code itself)_
    - <b>metadata.processing.preprocessor.*:</b> `#define`, `#ifdef` _(C-style preprocessor operatives)_
    - <b>metadata.processing.shebang.*:</b> `#!/usr/bin/env ruby -Ku` _(UNIX shell scripting shebangs)_
    - <b>metadata.processing.magic-comment.*</b> `# -*-mode: tcl; fill-column: 75; tab-width: 8; coding: iso-latin-1-unix -*- ` in emacs or `# encoding: utf-8` in Ruby _(other sorts of magic comments that affect the code)_

# Operators
The difference between operators and keywords bears some discussing. Operators
are almost always punctuation, whereas keywords are almost always textual.
There are exceptions to this rule (`and` and `or` are operators, because
they're simply alternatives to `&&` and `||`), but it's a good generalization.

- <b>operator.*</b>
  - <b>operator.comparator.*:</b> `<`, `>`, `<=`, `>=`, `==`, `===`
  - <b>operator.setter.*:</b> `=`, `+=`, `-=`, `*=`, `||=`
  - <b>operator.mathematical.*:</b> `+`, `-`, `*`, `/`, `%`
  - <b>operator.logical.*:</b> `!!`, `&&`, `||`, `^`, `!`, `&`, `|`

# Delimiters
Delimiters are things that, well, delimit. They mark the edges of things,
where one thing becomes another, or where two things become one.

- <b>delimiter.*</b>
  - <b>delimiter.balanced.*</b>
    - <b>delimiter.balanced.quote.*</b>
      - <b>delimiter.quote.balanced.double:</b> `"these"`
      - <b>delimiter.quote.balanced.single:</b> `'these'`
    - <b>delimiter.balanced.parenthesis.*:</b> `(these)`
    - <b>delimiter.balanced.square-brace.*:</b> `[these]`
    - <b>delimiter.balanced.curly-brace.*:</b> `{these}`
  - <b>delimiter.seperator.*</b>
    - <b>delimiter.seperator.property-of.*:</b> `::` in ruby
    - <b>delimiter.seperator.comma.*:</b> `,`
