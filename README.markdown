Espresso Sugar Standards
========================
This repository is a small attempt to see the creation of Espresso sugars
standardized.

You are under no obligation to follow the naming conventions indicated herein,
but the hope is that if most of us do so, that the vast majority of Espresso
themes will play well with the vast majority of Espresso Sugars.

Sugar developers
----------------
If you plan to make your Sugar compatible with this standard, there are
several rules.

While you can take individual parts and follow them, your sugar won't be valid
unless it fully adheres to the standard.

You may not use identifiers in the root categories that aren't in the standard.
If your Sugar creates it's own categories where no subcategories are allowed,
it isn't valid by this standard.

Certain categories (usually those at the 'deepest level' in the category tree)
allow you to extend them with whatever you please - these categories end with
`.*` in the spec file. For instance, if you were writing a Sugar for the
Python programming language, you might be tempted to attach Python's "tuple"
construct to an identifier of "literal.collection.tuple", since a tuple is
neither a set, nor an array. This would be invalid, because the
"literal.collection" category doesn't allow extension. Instead, you would
place tuples under one of the extensible categories, such as follows:
"literal.collection.set.tuple".

This may seem counter-intuitive or too restrictive, because it loses some
semanticity and might not map well to all languages. The purpose of this rule
is that it allows themers to simply theme every item listed in the spec, and
then their theme will apply to the most sugars in the best possible way. Even
though your tuple concept really isn't a set, it will still be themed by the
themer's "literal.collection.set" theme. This will provide the best experience
for the end-user, and doesn't really take any extra time on your part.

If the language you are writing a Sugar for has a syntactical construct/concept
that simply *can not* be accurately placed in the existing tree, you should
create a new 'x-' category, and then request that it be added to the spec.
The 'x-' prefix indicates to themers that they should not attempt to attach
importance to that element yet, because it is in flux. For instance, if you
believed that a Python tuple simply could *not* be accurately described by any
existing category, you could give it an identifier of "literal.collection.x-tuple",
and then request that the "literal.collection.tuple" category be added to the
spec.

Themers
-------
As described above in the "Sugar developers" section, I would request two
things of themers:

- That you attach a visual effect of some sort, whatever fits in with your
  theme, to every category in the spec. Elements in the same super-category
  should have a similar visual "feel" to them, if possible.
- That you don't attach visual effects to elements with a category that is
  prefixed by 'x-'. This indicates that that category is a language-specific
  extension, that won't be applicable to any other language. There's a good
  chance that those elements will be added to a future version of this spec.
  (This doesn't imply that you can't have Sugar-specific features in your
  theme, just restrict them to legal elements of the Sugar that are below one
  of the extensible trees)

Ownership
---------
Primarily, this is a repository created by myself (elliottcable) to display
openly the reasoning behind the naming system I plan to follow in the
[Ruby.sugar](http://github.com/elliottcable/ruby.sugar/ "elliottcable's Ruby.sugar on GitHub").
If themers want their themes to work with the Ruby sugar, or indeed, any sugar
I write, they'll have to (at least to some extent) adhere to parts of this
standard; and if other Sugar developers find it acceptable, they too can
benefit from themers adhering to this standard.

Contributions / comments are well accepted, please, let me know what you think.
Although I'm going to personally maintain this document, I'm certainly open to
other points of view (though I may not change the standard to match those
points of view unless I consider them especially compelling).

Commenting
----------
One thing worth noting - if you want to comment on the document's changesets
please do so using GitHub's commenting system:

- Comment on the appropriate line or section.
  - If your comment is about a specific identifier, comment on that
    identifier's line
  - If your comment is about a specific section, comment on that section's
    header's line
  - If your comment is about the structure / conceptualization of the entire
    document at the stage of a given commit, comment on the entire commit
- Don't enumerate all of your points / arguments in a single comment, it's a
  real pain to read - instead, split it up among the relevant lines or
  sections if at all possible