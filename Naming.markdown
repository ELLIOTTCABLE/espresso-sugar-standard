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
      - <b>metadata.comment.block.documentation.*:</b> RDoc/YARD, JavaDoc, phpDocumentor comments _(comments formulated in a way accepted by the community and documentation-generating-tools to be documentation-blocks)_
  - <b>metadata.preprocessor.*:</b> `#define`, `#ifdef` _(C-style preprocessor operatives)_
  - <b>metadata.shebang.*</b>

# Punctuation
These bits will often be parts of another structure, such as {} being part of
a Hash (literal.enumerable.dictionary) or a function definition or a horde of
other things.

- - <b>punctuation.*</b>
  - <b>punctuation.operator.*</b>
    - <b>punctuation.operator.comparator.*:</b> `<`, `>`, `<=`, `>=`, `==`, `===`
    - <b>punctuation.operator.setter.*:</b> `=`, `+=`, `-=`, `*=`, `||=`
    - <b>punctuation.operator.mathematical.*:</b> `+`, `-`, `*`, `/`, `%`
    - <b>punctuation.operator.logical.*:</b> `!!`, `&&`, `||`, `^`, `!`, `&`, `|`
  - <b>punctuation.delimiter.*</b>
    - <b>punctuation.delimiter.balanced.*:</b> _(each of these might include 'start' and 'end' varieties, and could tie into any dynamic delimeter-balancing functionality offered by Espresso)_
      - <b>punctuation.delimiter.balanced.parenthesis.*:</b> `(these)`
      - <b>punctuation.delimiter.balanced.square-brace.*:</b> `[these]`
      - <b>punctuation.delimiter.balanced.curly-brace.*:</b> `{these}`
    - <b>punctuation.delimiter.seperator.*</b>
      - <b>punctuation.delimiter.seperator.property-of.*:</b> `::` in ruby
      - <b>punctuation.delimiter.seperator.comma.*:</b> `,`
  - <b>punctuation.quote.*</b>
    - <b>punctuation.quote.double:</b> `"these"`
    - <b>punctuation.quote.single:</b> `'these'`
