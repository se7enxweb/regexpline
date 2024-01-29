# regexpline

Provides a regular expression datatype for server side validation of editor's content edits within eZ Publish.

A datatype extension for eZ Publish

License: GPL

Provides a regular expression datatype for eZ publish.


# What is it?

For end users it will look like the standard "Text line" datatype that ships with eZ publish.

The biggest difference is that the input will be validated against a regular expression. This enables you to make sure the input meets certain criteria.

It can act like a regular "Text line" datatype by allowing all input (regexp: /.*/).


# Features

A number between square brackets denotes the version number where said feature has been introduced.

If no indication is present, version 1.0 contains the feature.

- Check user input against a regular expression (Perl-compatible)
- Ability to specify multiple regular expression [2.0]
- Use regular expression subpatterns to be able to use parts of the input in the object name pattern
- Ability to customise the text that will be used in the object name pattern [1.1]
- Ability to supply a help text for users
- Required checks compatible with newer eZ publish versions (drafts ignore required fields)
- Information collection support
- Attribute filtering support
- Ability to define preset regular expressions in an ini file
- Ability to select multiple presets [2.0]
- Ability to specify an error message per regular expression / preset [2.0]
- Ability to display the datatype as a single text line or as a textarea (object edit) [2.0]
- Ability to negate regular expressions and presets [2.1]
- Support for has_content in templates [2.1]
- Stripping of tags with possibility to disable the stripping via the ini file [2.2]
- Control the size of both a text line and a text area in content/edit [2.2]
- Error messages in case class validation fails [2.3]
- Contentclass import & export
- i18n support
- PHP5 support for eZ Publish 4.x [3.0]


# Information

While editing a contentclass, you will be able to define how the content of a regexpline attribute will be validated.

You can choose two paths:
  1. Enter regular expressions directly in the class.
  2. Select one or more presets which have been defined in an INI file.

Path 1 is pretty straightforward. The interface will tell you what you can do. Each regular expression you enter can
have an error message that describes what should be done to meet the criteria. If you specify multiple regular expressions,
the input must match all three expressions.

Path 2 reads the settings from an INI file. You can define as many regular expressions provided you give each of them a
unique identifier. With that very same identifier, you can build and array of error messages too. This way, you can accomplish
the same thing as in Path 1 (custom messages per regular expression).

Something specific for Path 2 is if the regular expression is negated afterwards (input must NOT match the expression). The datatype
will then look for the error message identifier by the regular expression's unique identifier concatenated with '_negate'. This is of
course not needed if you take Path 1 (the regular expression will always be negated for that attribute and the error message can be
constructed to reflect that).

Any subpatterns in the regular expressions chosen for an attribute will be available for use in the object name pattern. The datatype
allows you to construct a custom string of these subpatterns. The custom string will then be used in real object name pattern if you
construct the contentclass to do so.


# Planned Features

These features are NOT available yet, but they're coming.

No planned features at the time of writing


# Requirements

- A suitable eZ publish version: 4.0.
- Knowledge of Perl Compatible Regular Expression syntax (http://www.php.net/manual/en/ref.pcre.php)


# Installation

You can always find the latest version of this extension @
http://pubsvn.ez.no/community/trunk/extension/regexpline

If you can't use SVN, you can also download the most recently released version from the Contributions section @
http://ez.no/community/contribs

- Extract or checkout the regexpline extension into the eZ publish 'extension' folder
- Activate the extension by means of the admin interface or by adding
  
  ActiveExtensions[]=regexpline

  to [ExtensionSettings] in site.ini.append(.php)
- Clear the template override cache to make sure eZ publish picks up the templates in the extension.


# Bugs? Comments? Wishes?

- Bugs: If you report a bug, please make sure you have a minimal testcase so I can reproduce the problem.
  If I can't reproduce it, I can't fix it.

- Comments: Nothing special here :)

- Wishes: Please provide a clear description.

Direct all (fan|bug|wish)mail at: hans <dotty> melis <atty> gmail <dotty> com

Please note that this datatype has been developed in my spare time, and is supplied as is. I'm not responsible for any data loss or failures. YMMV!


# Tips & Tricks

1. If you want to refer to the complete text that matched the regular expression in the object name pattern, you can use <0> as tag.


# Copyright

Regular Expression datatype for eZ publish 4.x

Copyright (C) 2005 - 2008  Hans Melis

This program is free software; you can redistribute it and/or modify
it under the terms of the GNU General Public License version 2 as
published by the Free Software Foundation.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program; if not, write to the Free Software
Foundation, Inc., 51 Franklin St, Fifth Floor, Boston, MA  02110-1301  USA
