Languages.xml extensions
========================
I've defined some extensions to the standard Espresso `Languages.xml` that
allow a Sugar developer to convey more information abut their Sugar. These
extensions primarily allow your Sugar to be indexed by my [Sugar Manager.sugar][]
and alexgordon's [Coffee House][].

  [Sugar Manager.sugar]: <http://github.com/elliottcable/sugar-manager.sugar/> "elliottcable's Sugar Manager.sugar on GitHub"
  [Coffee House]: <http://fileability.net/coffee/index.php> "Coffee House Sugar aggregator"

Usage
-----
These elements should be placed in a `<meta>` section of your `Languages.xml`
file, as follows:
    
    <?xml version="1.0" encoding="UTF-8"?>
    <settings>
      
      <language id="com.someone.something">
        <!-- You should already have this, if you're defining a language -->
      </language>
      
      <meta>
        <!-- Extension's elements go here -->
      </meta>
      
    </settings>
    
Elements
--------

## `<name>` (required)
The `<name>` element should contain, quite simply, the name of the sugar. In
the vast majority of cases, this is going to be identical to the name of the
folder in which the sugar's Language.xml file resides, but minus the `.sugar`
extension.
    
    <name>Django</name>
    
## `<description>`
This should be a short and succinct description of the sugar. No formatting is
guaranteed to be interpreted. This shouldn't often be longer than a sentance
or two.
    
    <description>Fully describes the Django web framework for Python</description>
    
## `<author>` (required)
The author's (your) name(s). May be multiple names seperated by ", ".
    
    <author>elliottcable, Alex Gordon</author>
    
## `<identifier>` (required)
Identifier string (for the whole sugar, not the same as the language string
above). Should probably look like 'tld.domain.Sugar.Language-name' or
'tld.domain.Sugar.Language-name.framework'. For example, 'com.mydom.Sugar.Ruby'
or 'com.mydom.Sugar.Ruby.Rails'.
    
    <identifier>name.elliottcable.Sugar.Python.Django</identifier>
    
## `<version status="">` (required)
This should store the current 'version string' of the sugar. If you change
this number, systems may prompt the user to update your sugar.

The `status` attribute must be one of the following
- `development`: Not working at all, still under active development in
   preparation for a preview version or a release
- `preview`: Working, but not fully functional. Intended as a 'feature preview'
   for beta testers or interested parties
- `release`: A release version, this is prepared for general use.
    
    <version status="preview">0.1b2</version>
    <!-- ...or... -->
    <version status="release">2.1</version>
    
## `<download format="">` (required)
This should provide a publicly-accessibe URL at which the sugar's uncompiled
sources can be accessed.

The 'format' attribute should be one of the following:
 - raw: Only to be used internally by systems. *Do not use*.
 - tgz: URL references a tarred GZIP
 - zip: URL references a zipfile
 - svn: URL references the Sugar directory's path in a SVN repository
 - git: URL references a publicly-accessible git upstream
 
In all cases, the archive/repository should have the Sugar directory as it's
root - that is, the Languages.xml file and Sugar folders (Syntaxes, Itemizers,
etc...) should all be directly within the root of the archive/ repository, not
within a subfolder.

This URL should point to the version of the sugar referenced by the `<version>`
tag in this same file, that is, don't simply point at the latest version (if
you're pointing at a downloadable file and not a repository).
    
    <download format="git">git://github.com/elliottcable/django.sugar.git</download>
    <!-- ...or... -->
    <download format="zip">http://stuff.elliottcable.name/django.sugar.2.1.zip</download>
    
## `<url>`
The 'home URL' of the Sugar. This could be a project website, your personal
website, or any URL at which the user could get more information about your
Sugar's features and purpose before installing it.
    
    <url>http://github.com/elliottcable/django.sugar/</url>
    
## `<dependencies>`
This is an array of dependency elements, each of which references the
identifier of a Sugar upon which this Sugar depends. Dependencies will be
automatically installed first if found, and this sugar will marked as
unavailable if it's dependencies are not found / unavailable.

This tag may be omitted, or left empty. Both will be assumed to mean that this
Sugar will work without any dependencies.
    
    <dependencies>
      <dependency id="name.elliottcable.Sugar.Python">Python</dependency>
    </dependencies>
    
## `<script interpreter="">`
A shell script / shell command to be executed after the sugar is acquired, but
before it is installed.

This will be executed with the downloaded and uncompressed directory as the
working directory. No other environment is guaranteed, so be as explicit as
possible. This is primarily intended for Cocoa sugars to compile themselves
before installation.

This tag may also appear more than once, though that should be avoided. Order
of execution is not guaranteed.

This tag may be omitted.
    
    <script interpreter="/bin/sh">/usr/bin/xcodebuild</script>
    
## `<build-directory>`
If it is not sufficient for your sugar to be copied verbatim into the Sugars
directory as-is, such as if your sugar is compressed into a sub-directory or
your sugar has to be compiled and then copied from a build folder, then you
should define a relative path to your *actual* `.sugar` folder here.

This tag may be omitted. It will default to copying this entire root directory
into the sugars directory.
    
    <build-directory>build/Release/Sugar Manager.sugar</build-directory>
    
