Sassy Modules
=======

`sassy-modules` is the holy grail of cascading styles sheets.

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
- Child classes are prefixed with a `_`
  - Why: It prevents clashing and having to create `crazyLongUniqueClassNames`
- One css class per element, as many modifiers as you fancy
  - Why: It's clean, simple, and fun.
- You cannot nest Sections
  - Why: By not nesting, all child classes must be contained to the Section which makes it easy to catch duplicate class names.


Installation
----

`git clone https://github.com/gkiely/sass-modules.git`

And import `module.scss` into your scss stylesheet.



Example
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
.Header {                                   // Site section

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
.Footer {                                   // Site section
  
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
%Text {}                                     // Module name

%Text-sml {                                  // Module property  
  font-size: .6em;
}

%Text-lge {                                  // Module property  
  font-size: 1.8em;
}

%Text-orange {                               // Module property  
  color: #e44b23;
}
```


List.scss
---
```scss
%List {}                                      // Module name

%List-horiz li {                              // Module property  
  display: inline-block;
}

%List-pipe li {                               // Module property  
  &:after{
    content: " | ";
  }
}
```



Please explain
---------

`.Header`
- Site section that can be re-used throughout the site. i.e. Header, Footer, Card, ImageSlider

`.-page`
- A modifier.

<a href="http://viget.com/extend/bem-sass-modifiers" target="_blank">Why this syntax?</a>