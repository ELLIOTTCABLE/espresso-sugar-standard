Capture naming policies
=======================
The naming of captures isn't nearly as important as the naming of zones, but
it still bears some consideration.

Language uniqueness
-------------------
Some Sugars have begun to add a final ".language-name" class to all of their
zones and captures, this is completely unnecessary. If a themer wants to
access elements unique to a specific Sugar, they can simply use a selector
that combines the language's identifier and the zone's identifier. An example
follows:
    
    sourcecode.ruby string.quoted.double
    
Pairing
-------
Certain elements have 'pairs' of zones or captures involved. For instance, the
opening and closing brackets on an Array literal, or (in the Ruby programming
language) the `begin` and `end` keywords bracketing a block of code.

To make these easy to access in all situations, add a final class to the
capture of the two elements, as follows:
    
    <capture number="0" name="punctuation.string.quote.begin"/>
    <capture number="1" name="punctuation.string.quote.end"/>
    
Or, if your element has more content or subzones, then:
    
    <starts-with>
      <expression>...</expression>
      <capture number="0" name="punctuation.string.quote.begin"/>
    </starts-with>
    <ends-with>
      <expression>...</expression>
      <capture number="0" name="punctuation.string.quote.end"/>
    </ends-with>
    
