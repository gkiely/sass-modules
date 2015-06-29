Sass Modules
=======

`sass-modules` is the holy grail of cascading styles sheets.

Get ready to:
- Enjoy writing css again
- Create clean, semantic class names
- Deliver gorgeously reusable code that will make your friends & family envy your greatness
- Produce efficient css

And
 - Navigate your code like a Caribbean Pirate


Ethos
----
> Importing a module should never output code

> Creating CSS class names should be simple and fun

> Modular code is reusable code


Rules
----
- Modules and Site Sections are capitilized
  - Why: They get their own files, which makes it easy to identify and navigate your file
- Child classes are prefixed with a _
  - Why: It prevents clashing and having to create `crazyLongUniqueClassNames`
- One css class per element, as many modifiers as you fancy
  - Why: It's clean, simple, and fun.
- You cannot nest Sections
  - Why: By not nesting, all child classes must be contained to the Section which makes it easy to catch duplicate class names.


Usage
-----

myapp.html
---
```html
<div class="Header -home"> 
    <div class="_title">Page title</div>
</div>

<footer class="Footer">
  <ul class="_linkList">
    <li class="_item"></li>
    <li class="_item"></li>
    <li class="_item"></li>
  </ul>
</footer>
```



Header.scss
---
```scss
.Header {                                   // Site Section

  // Modifiers
  //-----------------------
  &.-home {
    background: #000;                       // Modifier styles
  }
  
  // Children
  //-----------------------
  ._title {
    @include module(text, title, lge);      // Module styles
    
    margin-left: 3px;                       // Specific styles
    float: left;                            // Specific styles
  }
}
```


Footer.scss
---
```scss
.Footer {
  
  // Children
  //-----------------------
  ._linkList {
    @include module(List, horiz, pipe);     // Module styles

    padding-top: .625em;                    // Specific styles
    border: 1px #ccc dashed;                // Specific styles
  }
  ._item {
    @include module(Text, orange, sml);     // Module styles

    margin-left: 1.25em;                    // Specific styles
  }
}
```



Text.scss
---
```scss
%Text {}
%Text-sml {
  font-size: .6em;
}
%Text-lge {
  font-size: 1.8em;
}

%Text-orange {
  color: #e44b23;
}
```


List.scss
---
```scss
%List {}
%List-horiz li {
  display: inline-block;
}
%List-pipe li {
  &:after{
    content: " | ";
  }
}
```



mixins.scss
---
```scss
/**
 * module mixin
 * 
 * @param  $args...   1st: module name, rest: list of modifiers
 * @return placeholders
 */
@mixin module($args...){
  $module: nth($args, 1);
  
  @extend %#{$module};                            // Extend original module

  @if length($args) > 1{
    @for $i from 2 through length($args){         
      $item: nth($args, $i);
      @extend %#{$module}-#{$item};               // Extend module properties
    }
  }
}
```



Please explain
---------

.Header
> Site section that can be re-used throughout the site. i.e. Header, Footer, Card, ImageSlider

.-page
A modifier.

[Why this syntax?](http://viget.com/extend/bem-sass-modifiers)

