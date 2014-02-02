
# (S)CSS Style Guide for *Gang of Five*

We will be using SCSS (Sass) for our stylesheets.

Based on the [Google CSS style guide](http://google-styleguide.googlecode.com/svn/trunk/htmlcssguide.xml#CSS_Style_Rules).

# ID and Class Naming
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

# Formatting
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
