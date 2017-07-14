## HTML

### General Style Rules

#### Protocol

Omit the protocol from embedded resources.  

Omit the protocol portion (http:, https:) from URLs pointing to images and other media files, style sheets, and scripts unless the respective files are not available over both protocols.  

Omitting the protocol - which makes the URL relative - prevents mixed content issues and results in minor file size savings.  

**Not recommended**  

```html
<script src="http://www.google.com/js/gweb/analytics/autotrack.js"></script>
```

**Recommended**  

```html
<script src="//www.google.com/js/gweb/analytics/autotrack.js"></script>
```

* * *

### General Formatting Rules

#### Indentation

Use tabs! Do not mix tabs and spaces!

* * *

#### Capitalization

Use only lowercase.  

All code has to be lowercase: This applies to HTML element names, attributes, attribute values (unless text/CDATA), CSS selectors, properties, and property values (with the exception of strings).  

* * *

#### Trailing Whitespace

Remove trailing white spaces.  
 
Configure your editor to "show invisibles". This will allow you to eliminate end of line whitespace, eliminate unintended blank line whitespace, and avoid polluting commits.  
[Nicolas Gallagher's Idiomatic CSS](https://github.com/necolas/idiomatic-css)

* * *

### General Meta Rules

#### Encoding

Use UTF-8 (no BOM).  

Specify the encoding in HTML templates and documents via <meta charset="utf-8">. Do not specify the encoding of style sheets as these assume UTF-8.  

* * *

#### Comments

Use comments, but strip it out in the release code (so it's the responsibility of the front-end developer -> if you forget it, **you'll have to strip it out** from the release code - backend code...)

Explain code as needed, where possible.  

Use comments to explain code: What does it cover, what purpose does it serve, why is respective solution used or preferred?  

* * *

#### Action Items

Mark todos and action items with TODO.  

Highlight todos by using the keyword TODO only, not other common formats like @@.  

**Not recommended**  

```javascript
/* Todo: replace dummy JSON with real one */
// @@TODO: replace dummy JSON with real one
```

**Recommended**  

```javascript
// TODO: replace dummy JSON with real one
```

* * *

### HTML Style Rules

#### Document Type

Use HTML5.  

HTML5 (HTML syntax) is preferred for all HTML documents: `<!DOCTYPE html>.`

* * *

#### HTML Validity

Use valid HTML where possible.  

Use valid HTML code unless that is not possible due to otherwise unattainable performance goals regarding file size.  

* * *

#### Semantics

Use HTML according to its purpose.  

Use elements (sometimes incorrectly called "tags") for what they have been created for. For example, use heading elements for headings, p elements for paragraphs, a elements for anchors, etc.  

Using HTML according to its purpose is important for accessibility, reuse, and code efficiency reasons.
  
Use proper HTML5 elements, but don't overuse it! (like using article, section for everything, instead of simple divs)  

Don't make the code too complex only because of semantics (eg. using 3-4 elements for image captioning, instead of simple solutions)

* * *

#### Multimedia Fallback  

Provide alternative contents for multimedia.  

For multimedia, such as images, videos, animated objects via canvas, make sure to offer alternative access. For images that means use of meaningful alternative text (alt) and for video and audio transcripts and captions, **if available**.  

**Providing alternative contents is important for accessibility reasons:** A blind user has few cues to tell what an image is about without alt, and other users may have no way of understanding what video or audio contents are about either.  

(For images whose alt attributes would introduce redundancy, and for images whose purpose is purely decorative which you cannot immediately use CSS for, use no alternative text, as in alt="".)  
  
* * *  

#### Separation of Concerns

Separate structure from presentation from behavior.  

Strictly keep structure (markup), presentation (styling), and behavior (scripting) apart, and try to keep the interaction between the three to an absolute minimum.  

That is, make sure documents and templates contain only HTML and HTML that is solely serving structural purposes. Move everything presentational into style sheets, and everything behavioral into scripts.  

* * *  

#### Entity References

Use entity references.  

**Not recommended**  

```html
The currency symbol for the Euro is "€".
```

**Recommended**  

```html
The currency symbol for the Euro is &ldquo;&eur;&rdquo;.
```

* * *

#### Optional tags

Omit optional tags (optional).  

For file size optimization and scannability purposes, consider omitting optional tags. The HTML5 specification defines what tags can be omitted.  

(This approach may require a grace period to be established as a wider guideline as it’s significantly different from what web developers are typically taught. For consistency and simplicity reasons it’s best served omitting all optional tags, not just a selection.)  

Do not close self closing tags (`<br>`) 

* * *

#### type Attributes

Omit type attributes for style sheets and scripts.  

Do not use type attributes for style sheets (unless not using CSS) and scripts (unless not using JavaScript).  

Specifying type attributes in these contexts is not necessary as HTML5 implies text/css and text/javascript as defaults. This can be safely done even for older browsers.  

**Not recommended**  

```html
<link rel="stylesheet" href="//maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css" type="text/css">
<script src="//code.jquery.com/jquery-3.2.1.js" type="text/javascript"></script>
```

**Recommended**  

```html
<link rel="stylesheet" href="//maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css">
<script src="//code.jquery.com/jquery-3.2.1.js"></script>
```
 
* * *  

### HTML Formatting Rules

#### General formatting

Use a new line for every block, list, or table element, and indent every such child element.  

Indent them if they are child elements of a block, list, or table element.  

**If you run into issues around whitespace between list items it’s acceptable to put all li elements in one line. A linter is encouraged to throw a warning instead of an error.**  

Using `<li>` elements (as stated above) in one line is okay for me (the safest mode to get rid of the whitespace issue)  

* * *

#### HTML Quotation Marks

When quoting attributes values, use double quotation marks.  

Use double ("") rather than single quotation marks ('') around attribute values.  

* * *

## CSS
  
### CSS Style Rules

#### CSS Validity

Use valid CSS where possible.  

Unless dealing with CSS validator bugs or requiring proprietary syntax, use valid CSS code.  

Use tools such as the [W3C CSS validator](http://jigsaw.w3.org/css-validator/) to test.  

Use [CSS Lint](http://csslint.net/) to test.

Use your IDE's built-in linter (eg. WebStorm has a good one).  

* * *
 
#### ID and Class Naming

No IDs in CSS and use presentational class names.

Use meaningful class names.  

Generic names are simply a fallback for elements that have no particular or no meaning different from their siblings. They are typically needed as "helpers."  

**Ban on IDs in CSS.** There is literally no point in them, and they only ever cause harm.
[Harry Robert's CSS style](http://csswizardry.com/2012/04/my-html-css-coding-style/)

**Not recommended**  

```css
// Meaningless and uses ID
#yee-1901 {}
```

**Recommended**  

```css
// Presentational
.button-green {}
.clear {}
```

* * *

### ID and Class Name Style

Use ID and class names that are as short as possible but as long as necessary.  

Try to convey what an ID or class is about while being as brief as possible.  

Using ID and class names this way contributes to acceptable levels of understandability and code efficiency.
  
**Not recommended**  

```css
#navigation {}
.atr {}
```

**Recommended**  

```css
#nav {}
.author {}
```  

* * *

### ID and Class Name Delimiters

Separate words in ID and class names by a hyphen.  
  
Do not concatenate words and abbreviations in selectors by any characters (including none at all) other than hyphens, in order to improve understanding and scannability.  

**Not recommended**  

```css
.demoimage {}
.error_status {}
```

**Recommended**  

```css
#video-id {}
.ads-sample {}
```  

* * *

#### Type Selectors

Avoid qualifying ID and class names with type selectors.  

Unless necessary (for example with helper classes), do not use element names in conjunction with IDs or classes.  

Avoiding unnecessary ancestor selectors is useful for performance reasons.  

**Only include a selector that includes semantics. A span or div holds none. A heading has some. A class defined on an element has plenty.**  
[Jonathan Snook's SMACCS](http://smacss.com/)

**Not recommended**  

```css
ul#example {}
div.error {}
.error span {}
```

**Recommended**  

```css
#example {}
.error {}
.error .label {}
```
 
* * *

#### Using !important

**Never use !important!**  

If you have to use it, you did something wrong! It makes the code very hard to understand and debug, modify!

* * *

#### Shorthand Properties

Use shorthand properties where possible and only use xxx-top, xxx-bottom if needed for overwriting previous declarations!

CSS offers a variety of shorthand properties (like font) that should be used whenever possible, even in cases where only one value is explicitly set.  

Using shorthand properties is useful for code efficiency and understandability.  

Don't use magic numbers! Magic Numbers are unlucky. These are numbers that are used as quick fixes on a one-off basis. Example: .box { margin-top: 37px }.
[WordPress CSS Coding Standards](http://make.wordpress.org/core/handbook/coding-standards/css/)

**Not recommended**  

```css
border-top-style: none;
font-family: palatino, georgia, serif;
font-size: 100%;
line-height: 1.6;
padding-bottom: 2em;
padding-left: 1em;
padding-right: 1em;
padding-top: 0;
```

**Recommended**  

```css
border-top: 0;
font: 100%/1.6 palatino, georgia, serif;
padding: 0 1em 2em;
```

* * *

#### 0 and Units

Omit unit specification after "0" values.  

Do not use units after 0 values unless they are required.   
 
If the value of the width or height is 0, do not specify units.  
[ThinkUp CSS Style Guide](https://github.com/ginatrapani/ThinkUp/wiki/Code-Style-Guide:-CSS)

Unit-less line-height is preferred because it does not inherit a percentage value of its parent element, but instead is based on a multiplier of the font-size.
[GitHub CSS Style Guide](https://github.com/styleguide/css)  
[MDN on unit-less line-height](https://developer.mozilla.org/en-US/docs/Web/CSS/line-height)  

* * *

#### Leading 0s

Omit leading "0"s in values.    

Do not use put 0s in front of values or lengths between -1 and 1.  

```css
font-size: .8em;
opacity: .5;
```

* * *

#### Hexadecimal Notation

Use 3 character hexadecimal notation where possible.  

For color values that permit it, 3 character hexadecimal notation is shorter and more succinct.  

* * *

#### Prefixes

Prefix selectors with an application-specific prefix (optional).  

In large projects as well as for code that gets embedded in other projects or on external sites use prefixes (as namespaces) for ID and class names. Use short, unique identifiers followed by a dash.  

Using namespaces helps preventing naming conflicts and can make maintenance easier, for example in search and replace operations.  

```css
.adw-help {} /* AdWords */
.gemius-placeholder {} /* Gemius */
```

* * *

#### Hacks

**Avoid user agent detection as well as CSS "hacks" - try a different approach first.**  

It's tempting to address styling differences over user agent detection or special CSS filters, workarounds, and hacks. Both approaches should be considered last resort in order to achieve and maintain an efficient and manageable code base. Put another way, giving detection and hacks a free pass will hurt projects in the long run as projects tend to take the way of least resistance. That is, allowing and making it easy to use detection and hacks means using detection and hacks more frequently - and more frequently is too frequently.  

**We target modern browsers,** don't use hacks just to support bad, old browsers like IE < 9.  

Don't make the source code look ugly, because of them.  

* * *

### CSS Formatting Rules

#### Declaration Order

Use logical groups.

Logical groups:

- (SASS @extend)
- layout
- alignment
- typo
- looks
- others
- (SASS @include)

Property order listed:

- position
- content
- display
- width
- height
- top
- bottom
- left
- right
- padding
- margin
- overflow
- z-index
- opacity
- box-sizing (but we usually use SASS mixin for this)
- font-family (or use font shorthand)
- font-size
- font-weight
- text-align
- text-transform
- text-overflow
- text-decoration
- text-indent
- line-height
- color
- letter-spacing
- white-space
- border
- background
- transition (but we usually use SASS mixin for this)
- transform (but we usually use SASS mixin for this)

**IMPORTANT:** these rules will be overwritten by SASS rules (when using SASS specific stuff, eg. mixins, extend) But when writing simple CSS in SASS these rules are the valid ones.
  
* * *

#### Block Content Indentation

Indent all block content.  

Indent all block content, that is rules within rules as well as declarations, so to reflect hierarchy and improve understanding.  

```css
@media screen, projection {

	html {
        background: #fff;
        color: #444;
	}
  
}
```

* * *

#### Declaration Stops

Use a semicolon after every declaration.  

End every declaration with a semicolon for consistency and extensibility reasons.  

* * *

#### Property Name Stops

Use a space after a property name's colon.  

Always **use a single space** between property and value (but no space between property and colon) for consistency reasons.  

**Not recommended**  

```css
h3 {
	font-weight:bold;
}
```

**Recommended**  

```css
h3 {
	font-weight: bold;
}
```

* * *

#### Declaration Block Separation

Use a space between the last selector and the declaration block.  

Always use a single space between the last selector and the opening brace that begins the declaration block.  

The opening brace should be on the same line as the last selector in a given rule.  

**Not recommended**  

```css
h3{
	font-weight:bold;
}

h3
{
	font-weight:bold;
}
```

**Recommended**  

```css
h3 {
	font-weight: bold;
}
```

* * *

#### Selector and Declaration Separation

Separate selectors and declarations by new lines.  

Always start a new line for each selector and declaration.  

Long, comma-separated property values - such as collections of gradients or shadows - can be arranged across multiple lines in an effort to improve readability and produce more useful diffs.    
[Nicolas Gallagher's Idiomatic CSS](https://github.com/necolas/idiomatic-css)  

**Not recommended**  
  
```css
a:focus, a:active {
	position: relative; top: 1px;
	box-shadow: 1px 0 0 0 #000, 0 2px 1px 0 #f00 inset, 10px 10px 0 0 #333;
}
```
  
**Recommended**  
  
```css
h1,
h2,
h3 {
	font-weight: normal;
	line-height: 1.2;
	box-shadow: 1px 0 0 0 #000,
				0 2px 1px 0 #f00 inset,
				10px 10px 0 0 #333;
}
```

* * *

#### Rule Separation

Separate rules by new lines.  

Always put a blank line (two line breaks) between rules.
  
When using SASS, then put a blank line between the nested blocks!

```css
html {
	background: #fff;
}

body {
	margin: auto;
	width: 50%;
}

.container {

	h1 {}
	
	h2 {}
	
	.text {}

}
```

* * *

#### CSS Quotation Marks

Use single quotation marks for attribute selectors and property values.  

Use single ('') rather than double ("") quotation marks for attribute selectors or property values. **Do not use quotation marks in URI values (url()).**  

Exception: If you do need to use the @charset rule, use double quotation marks—single quotation marks are not permitted.  

**Not recommended**  
  
```css
html {
	font-family: "open sans", arial, sans-serif;
}
```
  
**Recommended**  
  
```css
html {
	font-family: 'open sans', arial, sans-serif;
}
```

* * *

### CSS Meta Rules

#### Section Comments

Group sections by a section comment (optional).  

If possible, group style sheet sections together by using comments. Separate sections with new lines.  

"This section heading is also prepended with a $. This is so that - when I do a find for a section - I actually do a find for $MAIN and not MAIN."  
  
In situations where it would be useful for a developer to know exactly how a chunk of CSS applies to some HTML, I often include a snippet of HTML in a CSS comment.    
[Harry Robert's CSS style](http://csswizardry.com/2012/04/my-html-css-coding-style/)

Comments that refer to selector blocks should be on a separate line immediately before the block to which they refer.  
[ThinkUp CSS Style Guide](https://github.com/ginatrapani/ThinkUp/wiki/Code-Style-Guide:-CSS)  

**Use Markdown syntax for commenting!**  
[Markdown syntax](http://daringfireball.net/projects/markdown/syntax)  

* * *

## SASS

### SASS attribute order

#### List @extend(s) First

```css
.container {
	@extends %base;
	...
}
```

Knowing right off the bat that this class inherits another whole set of rules from elsewhere is good.  

* * *

#### List "Regular" Styles Next

```css
.container {
	@extends %base;
	position: relative;
	display: block;
	...
}
```

The rule for listing regular styles is defined in the CSS section!  

* * *

#### List @include(s) Next

```css
.container {
	@extends %base;
	position: relative;
	display: block;
	@include transition(all .3s ease-out);
}
```

This visually separates the @extends and @includes as well as groups the @includes for easier reading. You might also want to make the call on separating user-authored @includes and vendor-provided @includes.  

* * *

#### Nested Selectors Last

```css
.container {
	@extends %base;
	position: relative;
	display: block;
	@include transition(all .3s ease-out);
	
	> .title {
		@extend %fonts;
		font-weight: bold;
	}
	
}
```

Nothing goes after the nested stuff. And the same order as above within the nested selector would apply.    

* * *

#### Maximum Nesting: 5 Levels Deep (including pseudo selectors)

```css
.container {
	
	> .title {

		.lead {
			
			.date {
			
				&:before {
					// no more
				}
				
			}
		}

	}
	
}
```

Chances are, if you're deeper than that, you're writing a crappy selector. Crappy in that it's too reliant on HTML structure (fragile), overly specific (too powerful), and not very reusable (not useful). It's also on the edge of being difficult to understand.      

* * *

#### Global and Section-Specific Sass Files Are just Table of Contents

In other words, no styles directly in them. Force yourself to keep all styles organized into component parts.  

**List Vendor/Global Dependancies First, Then Author Dependancies, Then Patterns, Then Parts**  

So the "table of contents" things comes together like:  

```css
// Vendor dependencies
@import 'bourbon';

// Authored dependencies
@import 'global/config';
@import 'global/mixins';

// Patterns
@import 'global/tabs';
@import 'global/tables';

// Sections
@import 'layout/header';
@import 'layout/footer';
```

* * *

#### Break Into As Many Small Files As Makes Sense
 
Use small modules, partial files!
 
There is no penalty to splitting into many small files. Do it as much as feels good to the project. I know I find it easier to jump to small specific files and navigate through them than fewer/larger ones.
 
```css
...

@import 'global/header/header';
@import 'global/header/logo';
@import 'global/header/nav';
@import 'global/header/login';
```

I'd probably do this right in the global.scss, rather than have global @import a _header.scss file which has its own sub-imports. All that sub-importing could get out of hand.  

* * *

#### Partials are named _partial.scss

This is a common naming convention that indicates this file isn't meant to be compiled by itself. It likely has dependancies that would make it impossible to compile by itself.  

* * *

#### Variablize All Common Numbers, and Numbers with Meaning

If you find yourself using a number other than 0 or 100% over and over, it likely deserves a variable. Since it likely has meaning and controls consistency, being able to tweak it enmasse may be useful.  

If a number clearly has strong meaning, that's a use case for variablizing as well.  

* * *

#### Variablize All Colors

Except perhaps white and black. Chances are a color isn't one-off, and even if you think it is, once it's in a variable you might see uses for it elsewhere.  
  
Variations on that color can often be handled by the Sass color functions like lighten() and darken() - which make updating colors easier (change in one place, whole color scheme updates).

Use the colors from the design swatches (ask for them, if you don't have them)  
  
* * *

#### Nest and Name Your Media Queries

The ability to nest media queries in Sass means:  
- 1) you don't have to re-write the selector somewhere else which can be error prone  
- 2) the rules that you are overriding are very clear and obvious, which is usually not the case when they are at the bottom of your CSS or in a different file.
  
```css
.sidebar {
	float: right;
	width: 33.33%;
	
	@include bp(mama-bear) {
        width: 25%;
	}
	
}
```

[More info](http://css-tricks.com/naming-media-queries/)

* * *


### JavaScript Language Rules

#### var

Declarations with var: always.

Use **one var declaration for multiple variables** and declare each variable on a newline.  

```javascript
// bad
var items = getItems();
var goSportsTeam = true;
var dragonball = 'z';

// good
var items = getItems(),
	goSportsTeam = true,
	dragonball = 'z';
```

Assign variables at the top of their scope. This helps avoid issues with variable declaration and assignment hoisting related issues.  

```javascript
// bad
function() {
	test();
	console.log('doing stuff..');

	//..other stuff..

	var name = getName();

	if (name === 'test') {
		return false;
	}

	return name;
}

// good
function() {
	var name = getName();

	test();
	console.log('doing stuff..');

	//..other stuff..

	if (name === 'test') {
		return false;
	}

	return name;
}
```

But! Make sure you do not impose any performance implications on the code itself

```javascript
// bad
function() {
	var name = getName(); // in a function call with no arguments, this call is unneccessary

	if (!arguments.length) {
		return false;
	}

	return name;
}

// good
function() {
	if (!arguments.length) {
		return false;
	}

	var name = getName();

	return name;
}

// or even
function() {
	var name;

	if (!arguments.length) {
		return false;
	}

	name = getName();

	return name;
}
```

#### Conditional Expressions & Equality

Use `===` and `!==` over `==` and `!=`.  

Conditional expressions are evaluated using coercion with the `ToBoolean` method and always follow these simple rules:  

+ **Objects** evaluate to **true**  
+ **Undefined** evaluates to **false**  
+ **Null** evaluates to **false**  
+ **Booleans** evaluate to **the value of the boolean**  
+ **Numbers** evalute to **false** if **+0, -0, or NaN**, otherwise **true**  
+ **Strings** evaluate to **false** if an empty string `''`, otherwise **true**  

#### Commas

Leading commas: **Nope.**  

```javascript
// bad
var once
  , upon
  , aTime;

// good
var once,
	upon,
	aTime;

// bad
var hero = {
	firstName: 'Bob'
  , lastName: 'Parr'
  , heroName: 'Mr. Incredible'
  , superPower: 'strength'
};

// good
var hero = {
	firstName: 'Bob',
	lastName: 'Parr',
	heroName: 'Mr. Incredible',
	superPower: 'strength'
};
```

#### Type Casting & Coercion

Perform type coercion at the beginning of the statement.  

Use `parseInt` for Numbers and always with a radix for type casting.  

If for whatever reason you are doing something wild and `parseInt` is your bottleneck and need to use Bitshift for [performance reasons](http://jsperf.com/coercion-vs-casting/3), leave a comment explaining why and what you're doing.  

#### Naming Conventions

Avoid single letter names. Be descriptive with your naming.  

Use camelCase when naming objects, functions, and instances.  

#### Constants

Use NAMES_LIKE_THIS for constant values.  

Use @const to indicate a constant (non-overwritable) pointer (a variable or property).  

Never use the const keyword as it not supported in Internet Explorer.  

#### Semicolons

Always use semicolons.  

#### Nested functions

Yes  

#### Function Declarations Within Blocks

No

**Do not do this**  

```javascript
if (x) {
	function foo() {}
}
```

**Recommended**  

```javascript
if (x) {
	var foo = function() {}
}
```

#### Exceptions

Yes.

#### Custom exceptions

Yes.

#### Standards features

Always preferred over non-standards features  

For maximum portability and compatibility, always prefer standards features over non-standards features (e.g., string.charAt(3) over string[3] and element access with DOM functions instead of using an application-specific shorthand).  

#### Wrapper objects for primitive types

No.

#### Multi-level prototype hierarchies

Not preferred.  

#### delete

Prefer this.foo = null.  

**Do not do this**  

```javascript
Foo.prototype.dispose = function() {
	delete this.property_;
};
```

**Recommended**  

```javascript
Foo.prototype.dispose = function() {
	this.property_ = null;
};
````

In modern JavaScript engines, changing the number of properties on an object is much slower than reassigning the values. The delete keyword should be avoided except when it is necessary to remove a property from an object's iterated list of keys, or to change the result of if (key in obj).  

#### Closures

Yes, but be careful.  

#### eval()

Only for deserialization (e.g. evaluating RPC responses).  

#### with() {}

No.

#### this

Only in object constructors, methods, and in setting up closures.  

#### for-in loop

Only for iterating over keys in an object/map/hash.  

#### Associative Arrays

Never use Array as a map/hash/associative array.  

#### Multiline string literals

No.

**Do not do this**  

```javascript
var myString = 	'A rather long string of English text, an error message \
				actually that just keeps going and going -- an error \
				message to make the Energizer bunny blush (right through \
				those Schwarzenegger shades)! Where was I? Oh yes, \
				you\'ve got an error and all the extraneous whitespace is \
				just gravy.  Have a nice day.';
```

**Recommended**  

```javascript
var myString = 	'A rather long string of English text, an error message ' +
				'actually that just keeps going and going -- an error ' +
				'message to make the Energizer bunny blush (right through ' +
				'those Schwarzenegger shades)! Where was I? Oh yes, ' +
				'you\'ve got an error and all the extraneous whitespace is ' +
				'just gravy.  Have a nice day.';
````

#### Array and Object literals

Yes.  

#### Modifying prototypes of builtin objects

No.  

#### Internet Explorer's Conditional Comments

No.  

#### 

* * *

### JavaScript Style Rules

#### Naming

In general, use functionNamesLikeThis, variableNamesLikeThis, ClassNamesLikeThis, EnumNamesLikeThis, methodNamesLikeThis, CONSTANT_VALUES_LIKE_THIS, foo.namespaceNamesLikeThis.bar, and filenameslikethis.js.  

Use full caps namespace names, eg. MYNAMESPACE.

#### Custom toString() methods

Must always succeed without side effects.  

#### Deferred initialization

Ok.

It isn't always possible to initialize variables at the point of declaration, so deferred initialization is fine.  

#### Explicit scope

Always.  

* * *

### Code formatting

#### Line Length

Each line of text in your code should be at most 80 characters long.  

#### Non-ASCII Characters

Non-ASCII characters should be rare, and must use UTF-8 formatting.  

#### Spaces vs. Tabs

Use tabs.

#### Function Declarations and Definitions

Parameters on the same line if they fit.  

#### Function Calls

On one line if it fits; otherwise, wrap arguments at the parenthesis.  

If the arguments do not all fit on one line, they should be broken up onto multiple lines, with each subsequent line aligned with the first argument. Do not add spaces after the open paren or before the close paren.  

If the function has many arguments, consider having one per line if this makes the code more readable.  

#### Conditionals

Prefer no spaces inside parentheses. The else keyword belongs on a new line.  

```javascript
if (condition) {  // no spaces inside parentheses
	...
} else if (...) {  // The else goes on the same line as the closing brace.
	...
} else {
	...
}
```

If must always always have an accompanying brace.

#### Loops and Switch Statements

Switch statements should use braces for blocks.  

Annotate non-trivial fall-through between cases.

Empty loop bodies should use {} or continue, but not a single semicolon.  

#### Curly Braces

Because of implicit semicolon insertion, always start your curly braces on the same line as whatever they're opening. For example:

```javascript
if (something) {
	// ...
} else {
	// ...
}
```

#### Blank lines

Use newlines to group logically related pieces of code. For example:  

```javascript
doSomethingTo(x);
doSomethingElseTo(x);
andThen(x);

nowDoSomethingWith(y);

andNowWith(z);
```

#### Binary and Ternary Operators

Always put the operator on the preceding line. Otherwise, line breaks and indentation follow the same rules as in other Google style guides.  

This operator placement was initially agreed upon out of concerns about automatic semicolon insertion. In fact, semicolon insertion cannot happen before a binary operator, but new code should stick to this style for consistency.  

```javascript
var x = a ? b : c;  // All on one line if it will fit.

// Indentation +4 is OK.
var y = a ?
	longButSimpleOperandB : longButSimpleOperandC;

// Indenting to the line position of the first operand is also OK.
var z = a ?
		moreComplicatedB :
		moreComplicatedC;
```

This includes the dot operator.  

```javascript
var x = a . b() . c();  // All on one line if it will fit.

// Indentation +4 is OK.
var y = foo .
	stuff() . moreStuff();

// Indenting to the line position of the first operand is also OK.
var x = foo.bar().
	doSomething().
	doSomethingElse();
```

#### Parentheses

Only where required.

Use sparingly and in general only where required by the syntax and semantics.  

**Never use parentheses for unary operators such as delete, typeof and void or after keywords such as return,** throw as well as others (case, in or new).  

#### Strings

Prefer ' over ".

For consistency single-quotes (') are preferred to double-quotes ("). This is helpful when creating strings that include HTML.  

#### Compiling

Required.

Use of JS compilers such as the Closure Compiler is required for all customer-facing code.  

#### Tips and Tricks

##### True and False Boolean Expressions

The following are all false in boolean expressions:  

+  null
+  undefined
+  '' the empty string
+  0 the number

But be careful, because these are all true:

+  '0' the string
+  [] the empty array
+  {} the empty object

##### Conditional (Ternary) Operator (?:)

**Instead of this:**

```javascript
if (val != 0) {
	return foo();
} else {
	return bar();
}
```

you can write this:  

```javascript
return val ? foo() : bar();
```

The ternary conditional is also useful when generating HTML:

```javascript
var html = '<input type="checkbox"' +
    (isChecked ? ' checked' : '') +
    (isEnabled ? '' : ' disabled') +
    ' name="foo">';
```

##### && and ||

These binary boolean operators are short-circuited, and evaluate to the last evaluated term. 

##### Properties

Use dot notation when accessing properties.  

```javascript
var luke = {
	jedi: true,
	age: 28
};

// bad
var isJedi = luke['jedi'];

// good
var isJedi = luke.jedi;
```

Use subscript notation `[]` when accessing properties with a variable.  

```javascript
var luke = {
	jedi: true,
	age: 28
};

function getProp(prop) {
	return luke[prop];
}

var isJedi = getProp('jedi');
```
 

* * *

