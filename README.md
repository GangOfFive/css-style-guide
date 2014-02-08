**Table of Contents**  *generated with [DocToc](http://doctoc.herokuapp.com/)*

- [(S)CSS Style Guide for Gang of Five](#scss-style-guide-for-gang-of-five)
	- [File names](#file-names)
	- [ID and Class Naming](#id-and-class-naming)
	- [Formatting](#formatting)
	- [SCSS](#scss)

# (S)CSS Style Guide for *Gang of Five*

We will be using SCSS (Sass) for our stylesheets.

Based on the [Google CSS style guide](http://google-styleguide.googlecode.com/svn/trunk/htmlcssguide.xml#CSS_Style_Rules).

## File names
 - Name your files using hyphens: `elephan.scss`, `original-name.scss`, and partials this way: `_ocean.scss`, `_banana-bread.css`.

## ID and Class Naming
 - Use meaningless or generic names, depending on what you need to do.
 
    ~~~css
    /* Not recommended: meaningless */
    #yee-1901 {}
    
    /* Not recommended: presentational */
    .button-green {}
    .clear {}
    /* Recommended: specific */
    #gallery {}
    #login {}
    .video {}
    
    /* Recommended: generic */
    .aux {}
    .alt {}
    ~~~
 - Try to keep the names short. Abbreviations are ok.

## Formatting
 - Use lowercase for attributes and values.
    ~~~css
      /* Bad */
      color: #E5E5E5;
      /* Good */
      color: #e5e5e5;
    ~~~

 - Use shorthand properties wherever possible.

    ~~~css
    /* Bad */
    border-top-style: none;
    font-family: palatino, georgia, serif;
    font-size: 100%;
    line-height: 1.6;
    padding-bottom: 2em;
    padding-left: 1em;
    padding-right: 1em;
    padding-top: 0;
    /* Good */
    border-top: 0;
    font: 100%/1.6 palatino, georgia, serif;
    padding: 0 1em 2em;
    ~~~
    
 - Do not use units after 0 values unless they are required.

    ~~~css
    margin: 0;
    padding: 0;
    ~~~

 - Do not use put 0s in front of values or lengths between -1 and 1.

    ~~~css
    font-size: .8em;
    ~~~

 - For color values that permit it, 3 character hexadecimal notation is shorter and more succinct.

    ~~~css
    /* Bad */
    color: #eebbcc;
    /* Good */
    color: #ebc;
    ~~~
 - Use a semicolon after every declaration.

    ~~~css
    /* Bad */
    .test {
      display: block;
      height: 100px
    }
    /* Good */
    .test {
      display: block;
      height: 100px;
    }
    ~~~
    
 - Always use a single space between property and value (but no space
   between property and colon) for consistency reasons.

    ~~~css
    /* Bad */
    h3 {
      font-weight:bold;
    }
    /* Good */
    h3 {
      font-weight: bold;
    }
    ~~~

 - Always use a single space between the last selector and the opening brace
   that begins the declaration block. The opening brace should be on the same
   line as the last selector in a given rule.

    ~~~css
    /* Bad: missing space */
    #video{
      margin-top: 1em;
    }
    
    /* Bad: unnecessary line break */
    #video
    {
      margin-top: 1em;
    }
    /* Good */
    #video {
      margin-top: 1em;
    }
    ~~~
 - Use single ('') rather than double ("") quotation marks for
   attribute selectors or property values. Do not use
   quotation marks in URI values (url()).

    ~~~css
    /* Bad */
    @import url("css/maia.css");
    
    html {
      font-family: "open sans", arial, sans-serif;
    }
    /* Good */
    @import url(css/main.css);
    
    html {
      font-family: 'open sans', arial, sans-serif;
    }
    ~~~
    
## SCSS

These are SCSS-specific guidelines. Mostly based on this: http://css-tricks.com/sass-style-guide/.
 - Do not commit CSS files into source control. Compiling the SCSS files is part of the deployment process.
 
 - Use variables whenever it makes sense.
    ~~~scss
    $zHeader: 2000;
    $zOverlay: 5000;
    $zMessage: 5050;
    $headerBg: #f00;
    $messageText: #000;
    
    .header {
      z-index: $zHeader;
      background-color: $headerBg;
    }
    .overlay {
      z-index: $zOverlay;
    }
    .message {
      z-index: $zMessage;
      color: $messageText;
    }
    ~~~
 
 - List @extends first.
 - List @includes next.
 - List "regular" styles next.
 - Nested selectors last.
    ~~~scss
    .weather {
      @extends %module; 
      @include transition(all 0.3s ease); // good, leverages cascade!
      background: LightCyan;
      > h3 {
        @include transform(rotate(90deg));
        border-bottom: 1px solid white;
      }
    }
    ~~~

 - Be generous with comments.

 - Break into as many small files as makes sense.
    ~~~scss
    @import "global/header/header/";
    @import "global/header/logo/";
    @import "global/header/dropdowns/";
    @import "global/header/nav/";
    @import "global/header/really-specific-thingy/";
    ~~~

