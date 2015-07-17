Sass Modules
=======

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

Sass-modules lets you to create reusable and customisable Sass modules.


1. Get it
----

`git clone https://github.com/gkiely/sassy-modules.git` 

And import `module.scss` in your Sass file.

OR

Copy the module.scss mixin into your project.



2. Make a module
----
- Create Modules with Sass placeholders.
- Create child modules using Parent-child syntax

```scss
%Text{
  font-size: 1em;
}
%Text-title{
  font-weight: bold;
}
```


3. Use your module
----
- The first argument is the module name, the following arguments are the module children.
```scss
@include module(Text, title);
```




Complete Example
-----
style.scss
```scss
.my-heading{
  @include module(Text, med, orange);
}
.my-list{
  @include module(List, reset);
  li{
    @include module(List, inline, pipe);
  }
}
```

Text.scss (module file)
```scss
%Text{
  font-family: Arial, sans-serif;
}

%Text-med{
  font-size: 1.3em;
}

%Text-orange{
  color: orange;
}
```

List.scss (module file)
```scss
%List{}

%List-reset{
  margin: 0;
  padding: 0;
  list-style-type: none;
}

%List-inline{
  display: inline-block;
}

%List-pipe{
  &:after{
    content: " | ";
  }
}
```