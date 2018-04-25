# Intro to Sass

## Learning Objectives

- **Explain** what Sass is and why it's used
- **Use** variables to make code more flexible
- **Understand** how to use nesting to help DRY up selectors and properties
- **Differentiate** between `@extend`, `@import`, `@mixin` & `@include`, and `@function`

## Framing: What is Sass?

![Sass Icon](http://sass-lang.com/assets/img/logos/logo-b6e1ef6e.svg)

---

### Syntactically Awesome Stylesheets

Sass is a superset of CSS that adds power and elegance to the basic language. You can do all the normal CSS things plus way more!
- You write a combination of CSS and SassScript, which compiles to proper CSS.
- It allows you to use variables, nested rules, mixins, inline imports and more, all with a fully CSS-compatible syntax.
- Sass helps keep large stylesheets well-organized, and helps get small stylesheets up and running quickly.

> Sass syntax originated from [Haml](http://haml.info/). Some developers didn't like a syntax that was so foreign from CSS and so the developers that created Sass introduced SCSS which is 'the new main syntax' for Sass.

<!--10:07 after intro talk in WDI3 -->
<!--9:58 after intro talk WDI4 -->
<!--11:25 10 minutes -->

## You Do: Explore Sass Examples

Explore these Codepens. When you open them, you'll notice that the CSS column has a header of `CSS (SCSS)`. This means that you're currently looking at Sass. Compare this to what you see when you click on the drop-down arrow at the top-right of the column and click "View Compiled CSS". Now you're looking at the CSS after it's been compiled from Sass.

Some things to consider...
* In what ways does Sass look different than Vanilla CSS?
* How might writing out Sass be easier / faster than writing out vanilla CSS?

#### Sass Examples

- [BAMSAY](http://codepen.io/jshawl/pen/cLJal)
- [Boxes](http://codepen.io/jshawl/pen/nHDLz)
- [Bullseye](http://codepen.io/jshawl/pen/wpeit)
- [A Button](http://codepen.io/jshawl/pen/bcjyH)
- [Forest](http://codepen.io/jshawl/pen/cJjIm)
- [Space Invader](http://codepen.io/jshawl/pen/cnyrJ)

> We don't expect you to understand exactly what the Sass is doing in these examples. Just think about it on a higher level.
### I. Variables

#### Questions

* What are Sass variables? What problem do they solve?
* How do you define a variable?
* What values can you store in a variable?
* What are some common use cases?
* How does scope work with Sass variables?

Sass allows us to use variables which are defined with `$`. Variables can store
strings, numbers, colors, arrays, and objects. Variable names should relate to
their usage and not their value e.g. ✅`$border-color` vs. ❌`$red`. One big
advantage to using variables it makes it easy to update properties.

#### Resources

* [Sass Documentation](http://sass-lang.com/guide)
* [Sass Variables](https://robots.thoughtbot.com/sass-variables)
* [Getting Started with Sass](http://alistapart.com/article/getting-started-with-sass)

### II. Nesting

#### Questions

* What does "nesting" mean in Sass? What problem does it solve?
* What does `&` mean?
* What's the difference between selector nesting and property nesting? Show examples of each.
* How much nesting is too much nesting?

#### Resources

* [Sass Documentation](http://sass-lang.com/guide)
* [The Inception Rule](http://thesassway.com/beginner/the-inception-rule)

### III. Extends & Inheritance

#### Questions

* What is Sass inheritance? What problem does it solve?
* How do we use `@extend` to implement inheritance?
* What does an `@extend` example look like when compiled to vanilla CSS.
* What are some common use cases?

#### Resources

* [Sass Documentation](http://sass-lang.com/guide)
* [Extending In Sass Without A Mess](https://www.smashingmagazine.com/2015/05/extending-in-sass-without-mess/)
* [The Extend Concept](https://css-tricks.com/the-extend-concept/)

### IV: Mixins

#### Questions

* What are mixins? What problem do they solve?
* How do we define and use a mixin?
* In what way might a mixin resemble a programming language?
* What is a common example of a mixin?

#### Resources

* [Sass Documentation](http://sass-lang.com/guide)
* [The Mixin Directive](https://www.sitepoint.com/sass-basics-the-mixin-directive/)
* [Handy Sass Mixins](https://web-design-weekly.com/2013/05/12/handy-sass-mixins/)
* [The Extend Concept](https://css-tricks.com/the-extend-concept/)

### V: Functions

If a group is looking for a challenge, look into Sass functions!

#### Resources

* [Sass Documentation](http://sass-lang.com/documentation/Sass/Script/Functions.html)
* [Pure Sass Functions](http://thesassway.com/advanced/pure-sass-functions)


<!--11:03 WDI3 -->

<!--12:15 5 minutes -->

## Compiling to CSS

Webpages don't know what to do with raw Sass/SCSS, these files need to be compiled to regular CSS to be used.

This can be done a number of different ways...
- Using a GUI program/plugin like `sass-autocompile`
  - For Atom: `apm install sass-autocompile`
  - For Sublime: [SassBuilder](http://www.hongkiat.com/blog/sublime-text-compiling-sass/)
- Letting a build tool like Grunt/Gulp/Webpack/npm-scripts handle the compilation with an additional package/plugin.

## Set Up
<!-- The starter code in this folder (`app`) is the solution code from our [Angular Directives Lab](https://github.com/den-materials/angular-directives-lab). It’s just a frontend, but that’s all we need to get started! -->
We have starter code that gives us a nice little front end to experiment with. Let’s start by initializing our repo with NPM and installing Gulp.

### 1. Initialize Node

Hopefully this step isn’t too distant a memory - but in case you’ve forgotten, `cd` into the `app` folder and run `npm init -y`.

### 2. Practice with your Racer Game or Project 1

Start a Python Simple Server to run your project:
`python -m SimpleHTTPServer`

### 3. Install Gulp

1. First, cd into the app folder, `cd` into it, and `npm init -y` your project
You’ll want to install gulp globally. You can do this by running the `npm install gulp -g` command.
1. We also need to include gulp in our project. To do that, we will run `npm install gulp --save-dev`. We use `--save-dev` because a production environment should not be concerned with build tools.
1. Touch a `gulpfile.js`
1. Define our default task:
```
var gulp = require('gulp');

//define a task with the name of 'default'
// and a callback to perform when the task is ran
gulp.task('default', function() {
  console.log('I am the default task. Hear me roar');
});
```
1. In your terminal, run `gulp`! You should see our default task run.
<!-- WDI6 3:12 handed to devs -->

### 4. Compile Sass

Now let's compile some Sass to CSS.  We need to start by requiring the `gulp-sass` plugin for Gulp.

```bash
npm install --save-dev gulp-sass
```

Then we can require it in our `gulpfile.js`.

```js
//gulpfile.js
var gulp = require('gulp');
var sass = require('gulp-sass');
```

Define a `styles` task that looks in a `/sass` directory for all `.scss` files, logs any errors that occur, and then compiles the result into a `/css` directory.

```js
gulp.task('styles', function() {
    gulp.src('sass/**/*.scss')
        .pipe(sass().on('error', sass.logError))
        .pipe(gulp.dest('./css/'));
});
```
Create a `/sass` directory and `touch` a `main.scss` file inside.

Run `gulp styles` and it will find your `.scss` file and output a corresponding `.css` file for you.

Lastly let's add the task we just created to gulp's `default` task and have it run the task upon file changes by watching the file. Now every time you save, your `.scss` will trigger the `styles` gulp task and compile the changes for you!
<!-- WDI6 3:28 turning over to devs -->
<!--11:32 when turning over to devs -->

To do this, at the bottom of your file add:

```js
gulp.task('default',function() {
    gulp.watch('sass/**/*.scss',['styles']);
});
```

Now we can run our Sass compilation with just `gulp`.

<!-- WDI6 3:39 turning over to devs -->

### 5. What the hell, let's add Browser Sync as well

Gulp is so cool. In addition to Sass Compiling, we can give our apps other neat tricks, such as using `Browser Sync` to reload our page every time a page is saved.

Start by installing `Browser Sync`:
`npm install browser-sync gulp --save-dev`

Next, we can rewrite our `gulpfile.js` to have `Browser Sync` watch our file, and reload every time a page changes:

```js
var gulp = require('gulp');
var sass = require('gulp-sass');
var browserSync = require('browser-sync').create();

// Static Server + watching scss/html files
gulp.task('serve', ['sass'], function() {

    browserSync.init({
        server: "./"
    });

    gulp.watch("sass/**/*.scss", ['sass']);
    gulp.watch("*.html").on('change', browserSync.reload);
});

// Compile sass into CSS & auto-inject into browsers
gulp.task('sass', function() {
    return gulp.src("sass/**/*.scss")
        .pipe(sass())
        .pipe(gulp.dest("./css/"))
        .pipe(browserSync.stream());
});

gulp.task('default', ['serve']);
```
>The above functions were contructed using [Browser Sync's Documentation](https://browsersync.io/docs/gulp)

You can stop your Python Simple Server now - `Browser Sync` is running the show now! Restart `gulp` and watch it go!
<!-- WDI6 3:52 turning over to devs -->
