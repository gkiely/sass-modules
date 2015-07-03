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
@include module(MyModule, propertyOne, propertyTwo)
```


Example
-----
style.scss
```scss
.my-heading{
  @include module(Text, med, orange);
}
```

Text.scss
```scss
%Text{
  font-family: 'Open sans', sans-serif;
}

%Text-med{
  font-size: 1.3em;
}

%Text-orange{
  color: orange;
}
```