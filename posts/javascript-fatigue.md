# JavaScript Fatigue

In the last 10 years, the web has grown quickly from a document-only platform to full-scale applications. A good chunk of the applications which are now being developed are no longer native, and are instead relying on the web.

This massive ecosystem change has not been painless and a lot of developers in the JavaScript community experience what could be called 'JavaScript Fatigue'.

There are now more than 350 different APIs listed on [Can I use](http://caniuse.com/) with various levels of browser support and an ever-expanding scope of JavaScript. JavaScript is also now commonly used on the server side with [Node.js](https://nodejs.org/en/) and on desktop with [Electron](http://electron.atom.io/) or [Node Webkit](https://github.com/nwjs/nw.js/).

## The tooling is complex

Keeping up with all these different technologies comes at a cost. Browsers are slower to update than the language and as a consequence, lots of tools have emerged to circumvent this problem.

[ES6](http://es6-features.org), the current JavaScript standard is partially incompatible with existing ES5 implementations so a transpiler must be used in production to make sure the code actually runs on most browsers. The next iterations of JavaScript, ES7 and ES8 are currently being specified.

A modern tooling can include [ES6](http://es6-features.org) and [JSX](https://facebook.github.io/react/docs/jsx-in-depth.html) transpilers, boilerplates, linters, minifiyers, [Bower](https://bower.io/) and [NPM](https://www.npmjs.com/) package managers.
In order to generate and run all of this reliably, some scripting must be used, [Grunt](http://gruntjs.com/) or [gulp](http://gulpjs.com/) are currently the most popular ones.

All of these tools are very complex to setup together so some project generators like [Yeoman](http://yeoman.io/) have appeared.

Even the summary itself of the most popular React generator on JavaScript for Yeoman clearly shows the problem by showing a large list of included tools:

```
React Starter Kit — isomorphic web app boilerplate (Node.js, Express, GraphQL, React.js, Babel 6, PostCSS, Webpack, Browsersync)
```

For a JavaScript novice or JavaScript developer coming from 2005, all of these technologies are new and understanding how each of them interact with each other can take a long time.

## Poor debuggability

Because the end result on the browser is very far from the developer source code, it becomes harder and harder to debug JavaScript applications. After passing through dozens of transpilers, minifiers and other code generators, the end source code actually executed is very different from what the developer sees.

Event debugging has also not improved very well in the past few years so understanding what triggered an action is now even more complex.

### Sourcemaps might not work very well

JavaScript sourcemaps are an attempt to provide some better debug stacktrace to heavily transformed JavaScript but sourcemaps also have their own shares of problems.

While all major browser now support sourcemaps, not every browser supports them to the same degree and, depending on the browser, the resulting stacktrace can sometimes be largely unhelpful.

The sourcemaps also need to be applied in the right order during all the tooling transformations, otherwise the resulting sourcemap might be incomplete or invalid.

## The environment is changing too quickly

### Client-side frameworks are constantly changing

Client side frameworks are appearing and disapearing very quickly. As an example, on the front-end side, we have:

- [Backbone](http://backbonejs.org/)
- [Knockout](http://knockoutjs.com/)
- [Batman](http://batmanjs.org/) - Now deprecated
- [Ember](http://emberjs.com/)
- [Angular](https://angularjs.org/) - Angular 2 has now very different semantics than the original Angular
- [React](https://facebook.github.io/react/) - The current trendy framework, made by Facebook.

All of them were popular at some point and then decreased in popularity, the current framework du jour is at the moment React.js, but for how long ?

The codebase still needs to be maintained, sometimes years after developing the code, but having a new trendy JavaScript framework every two years is expensive to maintain.

### The tooling is constantly changing

The tooling itself has also changed a lot in the past few years, here is a small list of technologies which have been experiencing changes:

- [CoffeeScript](http://coffeescript.org/): A language wrapper to make JavaScript nicer, since most of the improvements are now available in ES6, CoffeeScript seems to die slowly. Typescript is a new transpiler adding types to JavaScript which seems popular at the moment (for how long ?).
- [Require.js](http://requirejs.org/) / Webpack: Tools to bring the power of package managers to the browser, even if both are still popular, the new trend is now to use [Browserify](http://browserify.org/).
- [Grunt](http://gruntjs.com/): An equivalent of ```make(1)``` for [Node.js](https://nodejs.org/en/), the new tool du jour is now [Gulp.js](http://gulpjs.com/) and a lot of repositories are converting their codebase to the latter.
- [Babel](https://babeljs.io/), [Traceur](https://github.com/google/traceur-compiler), [Esnext](https://github.com/esnext/esnext) ...: The war for ES6 transpilers is still on and no clear winner can currently be observed.
- [SCSS](http://sass-lang.com/) / [SASS](http://sass-lang.com/) / [Less](http://lesscss.org/) / [PostCSS](https://github.com/postcss/postcss): The tooling war does not stop at the borders of the JavaScript world but also extends to CSS. SASS seems to be slightly more popular than Less at the moment but it's difficult to predict what will happen there.

### The language itself is constantly changing

ES6, the current addition to the language is not itself adopted, but talks are already focusing on ES7 and ES8.

The [ES6 compability table](https://kangax.github.io/compat-table/es6/) is now very large. This table is just the additions to the language itself, not considering the new Web APIs appearing almost every other week.

The UNIX philosophy seems a practice from a distant past. Every new API is now added to an ever-ending global window Object along with prefixes and checking API support is quite complex.

What counts on the browsers is now the speed of delivery, stability is only considered secondly. IndexDB barely works reliably between different browser implementations ([PouchDb](https://pouchdb.com/) as an example is using a lot of workarounds to make it work) and the HTML5 Offline Cache offers so little control that it's barely used in production despite having a lot of potential.

## Conclusion

As the JavaScript language is now properly maturing, the speed of change of the ecosystem should hopefully slow down a little bit and enable developers to actually let their projects age. I hope for a future where coding JavaScript applications is simpler and choosing tools much easier, while competition is a worthwhile goal, it is often at the expense of stability and simplicity.
