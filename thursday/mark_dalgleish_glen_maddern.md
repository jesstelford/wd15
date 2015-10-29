# CSS in the age of components

Mark Dalgleish

* Documents vs Web Apps
* Global scope vs Maintenance
  * In CSS Zen garden, global scope is OK
  * In large apps, not so much

## Solving Global CSS
How do we address the global css problem?

* OOCSS
* SMACSS
* BEM
  * Most popular
  * `.Block__Element--Modifier { ... }`
  * Try and limit scope of selectors
  * Only style those blocks and not let the style leak
  * When applied to your markup, it's very noisy.
* SUIT
* Inline styles (React)

## The age of components

* Web Components
* Polymer
* Angular Directives
* React Copmonents

Focus on React (but the principles apply elsewhere too)

Components aren't new. The idea of private CSS & images has been around for a
while. Great!

... Unless you use 3rd party components (eg; jQuery date picker contains a lot
of stuff / CSS you may not want).

### Building

Traditionally (gulp/grunt): Each build task tends to want to know ALL about your
CSS (eg: SASS) or ALL about your JS or ALL about your HTML, etc.

Now: Webpack.

Single dependency tree. Stop thinking about your asset types in isolation. They
go together. In sub-folders. Ie; Components.

React!

```javascript
require('./MyComponent.css');

export default () -> {
  <div className="MyComponent">
    <div class="MyComponent__Icon">Icon</div>
  </div>
}
```

Normally would blow up. on `.css` require. Webpack to the rescue!

So this one tool can know about ALL your file types instead of a single asset
type. But you still have to specify each type separately.

(ed: Err... How is that different from the "old" way?)

---

Back to BEM.

> A block is a component

_- BEM_

Wait, so is a React element. Let's marry them together.

> Never use a block outside a copmonent of the same name


JS+CSS together form a component.

[JS+CSS][JS+CSS][JS+CSS][JS+CSS] === a page

## Webpack's "local scope"

```javascript
import styles from './MyCompoent.css'
```

What is that?

Local scope lets you:

```css
:local(.header) { ... }
:local(.footer) { ... }
/* etc */
```

Becomes:

```css
._234lkjsflkjw { .. }
._dslfkj245lkjsf { .. }
```

But you don't have to care, you can access it inside your component as
`styles.header` and `styles.footer`... Whoa.

So;

> No more naming collisions

And no more global CSS (it's locally scoped to your component)!

---

Mark went all-in on this approach at Seek in Melbourne.

Now: All CSS files contain a wall of `:local(.whatever)` selectors everywhere.

> What if locally scoped CSS was the default?

They flipped the model: Don't have to specify `:local()` everywhere, instead
everything is a local by default, and you specify a `:global` where you need it
(rarely).

Became `postcss-local-scope` which turned `.class` into `:local(.class)`

> Have you thought about writing a starndard for CSS modules that others could
> implement? What you're doing could totally fix the CSS ecosystem if it's
> widely adopted.

Hence: [http://github.com/css-modules](CSS Modules) (with a funny, ironic logo)

Available in Webpack today. And Browserify, JSPM, a node `require` hook. Still
expanding.

---

Part 2: [http://twitter.com/glenmaddern](Glen Maddern)

## The rise of modular style

### Human interfaces vs machine interfaces

> Are we making better interfaces for ourselves, or bending to the whim of the
> machines we use?

The bad old days of "namespaced" JS:

```javascript
window.NAMESPACE = {}
window.NAMESPACE.foo = "foo"
```

But could accidentally be clobbered in the future by someone else's code.

Enter Chrome (better than IE). There was already work on _ServerJS_, but still
didn't have a way to include other modules and load it only once.

Wait, that sounds like our problem with global CSS!

Back to JS.

NodeJS. Then ServerJS becomes CommonJS. Node dug in and used it to great effect.

So, no more `window.NAMESPACE`, now you have:

```javascript
var dependency = require('./dependency.js');

module.exports = function() {
  // ...
}
```

#### CSS isn't JS

True, but the change (to modules) is the change we needed

Case Study: npm is a massive success. Thanks to a reliable way to include
modules.

The ecosystem is irevokably changed.

But that's in node.

Enter Browserify. Write your browser code as if it's on a server. It'll
implement the commonJS code for you.

No globals in the browser?

> You can change the human interface of a language wihtout needing to change the
> machine interface.

*CSS*

The machine interface hasn't moved on since 2008.

But the ecosystem has:

* Sass
* Less
* PostCSS

But CSS is still global :(

Interoperable CSS is born. (now part of CSS Modules)

* Compile target, not human interface
* Each file stands alone can ipmort others
* Unlocks power of Borwserify / webpack, etc

```css
:import("./dependency.css") {
  import-alias: export-from-dependency;
}
:export {
  exported-token: sometihng
}
```

Interopable CSS jumps in during the CSS Module processing to give us the final
output as an object requirable in your JS:

```javascript
require('./MyComponent.css');

export default () -> {
  <div className="MyComponent">
    <div class="MyComponent__Icon">Icon</div>
  </div>
}
```

(smiley)

---

## Modular Style

Ok, we have modular styles, now what?

Because we're fully controlling the building step is able to rename the
classnames for us (to help with debugging, or to help with saving bytes).

Eg: A component with 2 visual variants:

in BEM:

```css
.SubmitButton .SubmiButton--normal { ... }
.SubmitButton .SubmiButton--danger { ... }
```

In CSS modules:

```css
.base { ... }
.normal {
  compose: .base
  ...
}
.danger {
  compose: .base
  ...
}
```

(similar to SASS placeholders)

Breaks the 1-to-1 mapping beetween entities and the classes you have.

Now you can deconstruct your UI into classes while allowing your HTML to stay
clean.

Tend to this heirarchy:

```
styles/
  shared/
    colors.css
    typography.css
  components/
    submit-button.css
    nav-bar.css
```

> Single purpose files full of single purpose classes

> Define an API into your styles for your markup to use.

### The future

We've figured out a module system for CSS.

* Site-wide theming
* Publising reusable components w/ CSS
* Non-JS ecosystems
* Flexibility

Goes great with Brad Frost's _Atomic Design_ workflow. But everything is a
component.
* Atoms are components
* Molecules are components
* Organisms are components
* Pages are components

> Modular Style = Composable Classes

Thanks to [these folks](http://github.com/orgs/css-modules/people)

Slides: http://glenmaddern.com/slides/modular-style

## Q&A

> What about moving an existing SASS codebase?

It's already kinda similar: a `variables.scss` file, etc.

Then if you're doing BEM, etc, in the SASS, you can start incrementally
converting small parts (leaf nodes) to CSS Modules way.
