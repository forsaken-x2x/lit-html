# Change Log

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](http://keepachangelog.com/)
and this project adheres to [Semantic Versioning](http://semver.org/).

<!--
   PRs should document their user-visible changes (if any) in the
   Unreleased section, uncommenting the header as necessary.
-->

## Unreleased

* Refactored how template tags and `render()` are implemented so that all
  specialization of template syntax is done in tags, not `render()`, allowing
  for the mixining of templates of different syntaxes, and for hooks in 
  `render()` to change templates before they're initially processed.
* Added ShadyCSS support in lib/shady-render.js. It's exported render function
  will pass templates to ShadyCSS's `prepareTemplate()` function to process style
  tags and elements in the template for emulate CSS scoping.
* lit-extended: Attribute bindings with a `?` suffix on the name now act as boolean
  attributes. The attribute will be removed for falsey values and set to `''` for
  truthy values, matching the HTML specification behavior for boolean attributes.

## [0.8.0] - 2018-01-12

* Allow all valid HTML attribute names, including emoji and Angular-style
  `(foo)=` and `[foo]=` names.
* Drastically improved performance of the `repeat` directive.
* Fixed an issue with expressions directly following elements.
* Fixed numerous bugs with the `repeat` directive.
* Performance improvements for template setup
* Internal code cleanup
* Support synchronous thenables
* Added the `asyncAppend` and `asyncReplace` directives to handle async iterable values in expressions.

## [0.7.0] - 2017-10-06

* Added the `svg` template tag for creating partial SVG content
* Support for expressions inside tables and other elements with limited permitted content
* Only remove whitespace between elements, or at the start or end of elements
* Fixed bugs with rendering iterables
* A few IE/Edge fixes. Closer to full support.

## [0.6.0] - 2017-09-01

* Fixed removing event handlers when setting them to `undefined`.
* Allow the text "{{}}" to appear in templates.
* Optimized clearing of Parts.
* Added `unsafeHTML()` directive to bind values as HTML source.
* Optimizations, simplification and bug fixes of Array handling code.
* Update to extension API: added partCallback parameter to `render()`.
* Added the `directive()` decorator function to create directives. Functions values are no longer treated as directive by default, simplifying declarative event handlers.