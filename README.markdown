Espresso Sugar Standards
========================

- [Zone naming: Programming languages](../blob/master/Naming/Programming%20language%20zones.markdown)
- [Zone naming: Declarative languages](../blob/master/Naming/Declarative%20language%20zones.markdown)
- [Capture naming](../blob/master/Naming/Captures.markdown)
- [Languages.xml extensions](../blob/master/Languages.xml%20extensions.markdown)

This repository is a small attempt to see the creation of [Espresso][] [Sugars][]
standardized.

You are under no obligation to follow the conventions documented herein, but
my hope is that if most of us Sugar developers do so, that the vast majority
of Espresso themes will play well with the vast majority of Espresso Sugars.

  [Espresso]: <http://macrabbit.com/espresso/> "MacRabbit's Espresso text editor"
  [Sugars]: <http://macrabbit.com/espresso/extend/> "Sugar plug-ins for Espresso"

Usage
-----
Don't utilize this repository in your Sugar development, everything here is in
a state of flux. Each 'finished' release will be posted to the forums, please
build your sugars by the rules provided there. After a 'finished' release,
changes will continue to be made to this repository, which will be then
released as a new 'version' of the specification. Sugar developers and themers
should only work off of the latest release version, and they should mention
which version they adhere to (so that a user can tell which themes will fully
style which Sugars).

Ownership
---------
Primarily, this is a repository created by myself (elliottcable) to display
openly the reasoning behind the naming system I plan to follow in my
[Ruby][Ruby.sugar] and [Regex][Regex.sugar] Sugars. If themers want their
themes to work with any sugar I write, they'll have to adhere to parts of this
standard; and if other Sugar developers find it acceptable, they too can
benefit from themers adhering to this standard by conforming to this standard
as well.

Contributions / comments are well accepted, please, let me know what you think.
Although I'm going to personally maintain this document, I'm certainly open to
other points of view (though I may not change the standard to match those
points of view unless I consider them especially compelling).

  [Ruby.sugar]: <http://github.com/elliottcable/ruby.sugar/> "elliottcable's Ruby.sugar on GitHub"
  [Regex.sugar]: <http://github.com/elliottcable/regex.sugar/> "elliottcable's Regex.sugar on GitHub"

Commenting
----------
One thing worth noting — if you want to comment on the document's changesets
please do so using GitHub's commenting system:

- Comment on the appropriate line or section.
  - If your comment is about a specific identifier, comment on that
    identifier's line
  - If your comment is about a specific section, comment on that section's
    header's line
  - If your comment is about the structure / conceptualization of the entire
    document at the stage of a given commit, comment on the entire commit
- Don't enumerate all of your points / arguments in a single comment, it's a
  real pain to read — instead, split it up among the relevant lines or
  sections if at all possible
