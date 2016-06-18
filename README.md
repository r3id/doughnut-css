# Why Doughnut?
Doughnut is a simple, easy to use, responsive CSS boilerplate, built using Sass, which can help kickstart any project into life.

Generally most projects don't need all the complexities of the larger frameworks, which makes Doughnut a great solution for you. Based around our grid system, Doughnut only styles a small selection of common HTML elements as this is more than often enough to get you started. This also allows you full flexibility over your design.

While planning DoughnutCSS I set myself 3 main goals which I wanted to achieve:-
- I wanted to be able to call classes anything I wanted, and not be constrained by naming conventions that didn't suit my project.
- I felt that not all designs needed margin ("gutters") on columns, so wanted to be able to add more or less margin if required.
- Most important I wanted it to be mobile first, as I have found that to be the best way of working.

Please visit [http://doughnut.r3id.io](http://doughnut.r3id.io) for a more detailed docs.
Current version: 2.0

## Getting Started
To get the most out of Doughnut you will need to a way to compile Sass. I use [Jekyll](http://jekyllrb.com) to build a lot of sites, but I have also found [Prepros](https://prepros.io) to be a fantastic stand alone app which works on Mac and Windows. Microsoft also provides a [Web Compiler](https://visualstudiogallery.msdn.microsoft.com/3b329021-cd7a-4a01-86fc-714c2d05bb6c) for Visual Studio which works a treat. If you don't want to compile Sass, I have included the "glazed" version of Doughnut which includes preset column names.

So, you're happy to compile Sass, now you will need to get your hands on Doughnut.

- Once downloaded you will need to add the `_sass folder` to your project.
- To get you started I have included a `main.sass` file in the assets folder.
- Use this main.sass file to create all your styles, or...
- ... create separate files using the `_components.filename.scss` for each component.

Using the `_components.filename.scss` method will allow you to create a much more maintainable codebase.

## Grids the basics
To get started create yourself a `.container`, then add a `.row` finally slap in our columns. It really is as easy as 1-2-3!

``` html
<div class="container">
  <div class="row">
    <div class="col sidebar">
       <!-- add your content here -->
    </div>
    <div class="col main">
       <!-- add your content here -->
    </div>
  </div>
</div>

```

Next you will need to build up you CSS classes and this is where doughnut really shines. By using `@extend` and one of our predefined placeholders in you class, you can create meaningful layout classes, and only use the sizes you need. You are also able to hide classes across the different breakpoints.

``` SASS

.sidebar {
  @extend %col-4;

  @include desktop {
    // add your desktop specific decelerations here.
  }

  // add your decelerations here.
}

.main {
  @extend %col-8;

  // add your decelerations here.
}

```

Doughnut uses a *Mobile First* strategy which means all styles outside of media queries will apply to all devices, larger screen sizes are then targeted for enhancement. This helps to prevent smaller devices having to parse tons of unused CSS.
