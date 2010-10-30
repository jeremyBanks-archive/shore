Shore
=====

Source: [github.com/jeremybanks/shore](http://github.com/jeremybanks/shore)  
Demo: [jeremybanks.github.com/shore](http://jeremybanks.github.com/shore/)

About
-----

Shore is a math library implemented in CoffeeScript. A browser interface is
included, along with the compiled JavaScript, so it should be usable on its
own or as library "out-of-the-box".

Developed with Chrome, should work the same in Safari, a bit less polished in 
Firefox and Opera, and remain functional in IE.

The interface has a LaTeX-style output format that requires you download
MathJax to `dep/MathJax`. If you do not it will fall back to plain-text output,
but at least for the moment this isn't given much attention.

Using the library on its own requires only `shore.*`, but you'll
probably also want to include `shore.parser.*`.

It is intended that this will eventually be able to gracefully degrade in the
absence of JavaScript and allow the calculations to be performed server-side,
presumably using node.js. But not yet.

Modifying the parser requires node.js and Jison.

Credits
-------

Author: Jeremy Banks <<jeremy@jeremybanks.com>>

Shore makes use of the following:

  - [CoffeeScript](http://jashkenas.github.com/coffee-script/)
  - [Jison](http://zaach.github.com/jison/)
  - [jQuery](http://jquery.com/) and the
    [Address plugin](http://www.asual.com/jquery/address/)
  - [MathJax](http://www.mathjax.org/)

See `LICENSE` file for copyright/license information.

Documentation
-------------

There'll be some once version 1.0 is finished.

TODO
----

### `v0.1`

  - Canonization of `shore.Sum`, `shore.Product`.
  - Merge `shore.Exponent` into `shore.Product`.
  - All defining attributes go onto `shore.Value().components`, which can
    typically be canonized without requiring class-specific code.
    That'd manage _eq nicely as well.
  - Support engineering notation in `shore.parser`.
  - Maybe put interface in main.html and only have an index.html in gh-pages.

### `v0.2`

  - Complete initial version of `shore.WithMarginOfError`.
  - Complete initial version of `shore.Derivative`.
  - Complete initial version of `shore.Integral`.
    - No support for anything difficult.
  - Pretty formatting for `shore.Number`?

### `v1.0`

  - Make the code decent
  - Write at least some basic documentation
  - Documentation!
  - Organize code better, clearly distinguishing library from interface.

### `v1.1`

  - `shore.System`
    - Parsed from multiline input.
    - Can substitute value to solve simple systems.
    - Maybe add/remove restrictions where appropriate?

### `v1.2`

- `shore.Inequality`
  - Just ≠ for now.
- `shore.Restricted`
  - Implications of potential division by zero, and such.

### Non-concrete Future Thinkings

  - Memoization.
  - Abstract away identifier values.
  - Support HTML5 offline cache?
  - Make nice on iPod touch/iPhone.
  - Maybe allow more classical functions via subscripts:
    fib_n = fib_(n-1) + fib_(n-2); fib_0 = fib_1 = 1
