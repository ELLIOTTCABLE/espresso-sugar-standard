# Literals
A literal is an element that is directly typed into the source code. In
some languages, these might be called constants - however, I consider that too
ambiguous, as most languages which Espresso users will often come across, a
constant means something else entirely (see `keyword.constant`).

- <b>literal.*</b>
  - <b>literal.string.*</b>
  - <b>literal.regex.*</b>
  - <b>literal.numeric.*</b>
  - <b>literal.enumerable.*</b>
    - <b>literal.enumerable.array.*</b>
    - <b>literal.enumerable.dictionary.*</b>

# Identifiers
An identifier is a syntatical element that uniquely identifies one object of
some sort in the language. This isn't restricted to the Object-Oriented
Language definition of 'object', this also means anything in a language which
can be referenced in some way.

- - <b>identifier.*</b> 
  - <b>identifier.function.*:</b> `func(1, 2, 3)`, referring to a identifier that points to a specific function - such as a function/method call
  - <b>identifier.variable.*</b> - $var, @var, @@var, Var
    - <b>identifier.variable.constant.*</b> - $var, Var

# Keywords
A keyword is an element defined in the language's definition itself - it can't
be changed by the programmer, and it usually invokes or references something
hardcoded into the language's compiler/parser/interpreter.

- - <b>keyword.*</b>
  - <b>keyword.control.*</b> - used for loops, conditionals and general flow control
    - <b>keyword.control.exception.*</b> - used to manage exceptions (raise, rescue, ensure, throw, catch)
    - <b>keyword.control.flow.*</b> - changes the 'direction' of the executing code (while, for, break, goto, if/then/else)
  - <b>keyword.modifier.*</b> - used for tacking onto declarations (abstract, public, private, etc)
    - <b>keyword.modifier.scope.*</b> - changes the 'scope' of a particular declarations (public, private, etc)
  - <b>keyword.definition.*</b> - used for creating or modifying a <b>block.*</b> element (class, function, method, module, begin, lambda)
  - <b>keyword.type.*</b>
  - <b>keyword.literal.*</b>
    - <b>keyword.literal.constant.*</b> - nil, true, false, undefined, NaN, etc

# Blocks
These are less being defined for the purpose of highlighting, and more for use
in attaching Itemizers, and for the purpose of the subzones. Anything that is
a block of code should go here.

- - <b>block.*</b> - used for anything that attaches a block of code to something, such as a definition, iterator, or closure
  - <b>block.typedef.*</b>
    - <b>block.typedef.class.*</b>
    - <b>block.typedef.module.*</b>
    - <b>block.typedef.prototype.*</b>
  - <b>block.function.*</b>
  - <b>block.iterator.*</b>
  - <b>block.closure.*</b> - any block of code that acts as exactly that, a block of code packaged into a variable (lambda {} in Ruby, anonymous function in JavaScript)

# Metadata
This is mostly for comments - I can't think of anything else to go under this
heading, but there may be such things.

- - <b>metadata.*</b> - for information that will be ignored by the compiler/interpreter
  - <b>metadata.comment.*</b>
    - <b>metadata.comment.line.*</b>
      - <b>metadata.comment.line.shebang.*</b>
    - <b>metadata.comment.block.*</b>
      - <b>metadata.comment.block.documentation.*</b> - comments formulated in a way accepted by the community to be documentation-blocks
  - <b>metadata.preprocessor.*</b> - C-style preprocessor operatives, such as #define or #ifdef

# Punctuation
These bits will often be parts of another structure, such as {} being part of
a Hash (literal.enumerable.dictionary) or a function definition or a horde of
other things.

- - <b>punctuation.*</b>
  - <b>punctuation.operator.*</b> - for example + / :: -> < => == ===, etc
    - <b>punctuation.operator.comparator.*</b> - < > <= >= ==
    - <b>punctuation.operator.setter.*</b> - = += -= *= ||=
    - <b>punctuation.operator.mathematical.*</b> - + - * / %
    - <b>punctuation.operator.logical.*</b> - !! && || ^ ! & |
  - <b>punctuation.bracket.*</b> - (brackets) [of] {all} |different| /kinds/ 'and' "flavours"
    - <b>punctuation.bracket.quote*</b>
      - <b>punctuation.bracket.quote.double</b> - "these"
      - <b>punctuation.bracket.quote.single</b> - 'these'
    - <b>punctuation.bracket.balanced.*</b>
      - <b>punctuation.bracket.balanced.parenthesis.*</b> - (these)
      - <b>punctuation.bracket.balanced.square.*</b> - [these]
      - <b>punctuation.bracket.balanced.curly.*</b> - {these}
