Sassy Modules
=======

`sassy-modules` lets you to create reusable and customisable Sass modules.

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
  @include module(Text, title, lge, border);
}
```


Getting started
----

`git clone https://github.com/gkiely/sassy-modules.git`

And import `module.scss` in your Sass file.


Guidelines
----
- Modules are created with placeholders.
- The first argument is the module name, the following args are the module properties. *(Naming convention is optional)*.
```scss
@include module(My-module, property-one, property-two)
```


Example
-----

Coming soon.
