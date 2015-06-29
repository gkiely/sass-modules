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
  - Why? They get their own files, which makes it easy to identify and navigate your file
- Child classes are prefixed with a _
  - Why? It prevents clashing and having to create `crazyLongUniqueClassNames`
- One css class per element, as many modifiers as you fancy
  - Why? It's clean, simple, and fun.
- You cannot nest Sections
  - Why? By not nesting, all child classes must be contained to the Section which makes it easy to catch duplicate class names.


Usage
-----

myapp.html
---
```html

<div class="Header -page">
  <div class="_content">
    <div class="_logo">
    </div>
  </div>
</div>

<div class="Content">
  <h1 class="_title"></h1>
  <p class="_content"></p>
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
.Header{
}
```



MyModule.scss
---


Please explain
---------

.Header:
> Site section that can be re-used throughout the site. i.e. Header, Footer, Card, ImageSlider

-page
A modifier.

[Why this syntax?](http://viget.com/extend/bem-sass-modifiers)

