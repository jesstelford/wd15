# Advanced Responsive Topography

Mike Riethmuller

## Intro

Stop thinking in pixels!

This isn't the smae old .htc files.

An alternative approach to responsive design.

Relative units are really just an abstraction of pixels (eg; base font size of
16px)

Grids, media queries, make us feel better about being inside a constrained
environment.

Limitations shape our thinking. Eg; we have to think in pixels for media query
breakpoints.

Even perceived limitations can shape our thinking.

## Breaking the paradigm of pixels

### Unit Types & Values in CSS

"_Values_" can be functions, numbers, names, keywords, etc

eg;

```css
font-size: 24px
width: 80%
text-align: left
```

A browser turns these _values_ into _copmuted values_.

Ie; There are things the browser doesn't know until it starts rendering the
page.

* *initial* value is the value we specified
* *computed* value is used by browser initially
* *used value* final value used when rendering the page

#### `calc`

Basic arithmetic in CSS: addition, multiplication, etc. Be warned! There are
some caveats

Eg;
```css
calc(12px + 2rem); /* 42px (1rem === 16px) */
```

---

Instead of existing "responsive" techniques with media queries which are jumpy.
We can use viewport sizes. But that also has limitations.

Use:

```css
font-size: calc(18px + 3vw); /* min font size of 18px */
```

```css
html { font-size: 18px;}
@media (min-width: 600px) {
  html {
    font-size: 3vw;
  }
}
```

why 600px?

18 / (3 / 100) = 600px

font-size / (viewport_width / 100) = media query

A quick reference helps:

| | 1vw | 2vw
| --- | --- | ---
| 400px | 4px | 8px
| 500px | 5px | 10px


font-size: calc(12px + (24 - 13) * (100vw - 400px) / (800 - 400));

12px == min font size
(34 - 12) == max font size - min font

(100vw - 400px) == min screen size

(800 - 400) max screen size - 

### Modular Scale

Use _Modular Scale_. Nature uses this commonly (golden ratio, etc).

To calculate, divide or multiply the previous result by the ratio.

Eg; for `2`:

* 8 * 2 = 16
* 16 * 2 = 32
* 32 * 2 = 64

By using this, it creates fluid variations in the scale, not just in the size.

### Note just Typography!

Works also on svg icons (tomatos!)

### It's confusing :/

Forget everything you just learned and use SASS!

Sass mixin allows you to just plug it into your styles. [See [Mike's
blog](http://madebymike.com.au/writing/fluid-type-calc-examples)]
