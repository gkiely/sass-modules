Sassy Modules
=======

`sassy-modules` allows you to create reusable sass/scss modules.

Turn this:

```scss
.heading-title {
  font-size: 2.25em;
  line-height: 1.2;
  color: #333;
  font-weight: bold;
  padding-bottom: .3em;
  border-bottom: 1px solid #eee;
}
```

Into this:
```scss
.heading-title{
  @include module(Heading, title, lge, border);
}
```


Rules
----
- All modules should be created with placeholders. 
  > <a href="http://thesassway.com/intermediate/a-standard-module-definition-for-sass#a-module-is-a-unit-of-code-contained-in-a-partial">(Importing a module should never output code)</a>
- The module name should be named with an uppercase for readability.


Installation
----

`git clone https://github.com/gkiely/sass-modules.git`

And import `module.scss` in your scss/sass stylesheet.



Example
-----

Coming soon.
