<!--

@license Apache-2.0

Copyright (c) 2018 The Stdlib Authors.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

-->


<details>
  <summary>
    About stdlib...
  </summary>
  <p>We believe in a future in which the web is a preferred environment for numerical computation. To help realize this future, we've built stdlib. stdlib is a standard library, with an emphasis on numerical and scientific computation, written in JavaScript (and C) for execution in browsers and in Node.js.</p>
  <p>The library is fully decomposable, being architected in such a way that you can swap out and mix and match APIs and functionality to cater to your exact preferences and use cases.</p>
  <p>When you use stdlib, you can be absolutely certain that you are using the most thorough, rigorous, well-written, studied, documented, tested, measured, and high-quality code out there.</p>
  <p>To join us in bringing numerical computing to the web, get started by checking us out on <a href="https://github.com/stdlib-js/stdlib">GitHub</a>, and please consider <a href="https://opencollective.com/stdlib">financially supporting stdlib</a>. We greatly appreciate your continued support!</p>
</details>

# EPS

[![NPM version][npm-image]][npm-url] [![Build Status][test-image]][test-url] [![Coverage Status][coverage-image]][coverage-url] <!-- [![dependencies][dependencies-image]][dependencies-url] -->

> Difference between one and the smallest value greater than one that can be represented as a [double-precision floating-point number][ieee754].

<section class="intro">

[Epsilon][machine-epsilon] is defined as

<!-- <equation class="equation" label="eq:epsilon_float64" align="center" raw="\epsilon = b^{-(p-1)}" alt="Epsilon for a double-precision floating-point number."> -->

```math
\epsilon = b^{-(p-1)}
```

<!-- <div class="equation" align="center" data-raw-text="\epsilon = b^{-(p-1)}" data-equation="eq:epsilon_float64">
    <img src="https://cdn.jsdelivr.net/gh/stdlib-js/stdlib@6e1cf583c4854b3d982f22f361f53a30c9f552dc/lib/node_modules/@stdlib/constants/float64/eps/docs/img/equation_epsilon_float64.svg" alt="Epsilon for a double-precision floating-point number.">
    <br>
</div> -->

<!-- </equation> -->

where `b` is the radix (base) and `p` is the precision (number of radix bits in the significand). For [double-precision floating-point numbers][ieee754], `b` is `2` and `p` is `53`.

</section>

<!-- /.intro -->



<section class="usage">

## Usage

To use in Observable,

```javascript
EPS = require( 'https://cdn.jsdelivr.net/gh/stdlib-js/constants-float64-eps@umd/browser.js' )
```
The previous example will load the latest bundled code from the umd branch. Alternatively, you may load a specific version by loading the file from one of the [tagged bundles](https://github.com/stdlib-js/constants-float64-eps/tags). For example,

```javascript
EPS = require( 'https://cdn.jsdelivr.net/gh/stdlib-js/constants-float64-eps@v0.1.1-umd/browser.js' )
```

To vendor stdlib functionality and avoid installing dependency trees for Node.js, you can use the UMD server build:

```javascript
var EPS = require( 'path/to/vendor/umd/constants-float64-eps/index.js' )
```

To include the bundle in a webpage,

```html
<script type="text/javascript" src="https://cdn.jsdelivr.net/gh/stdlib-js/constants-float64-eps@umd/browser.js"></script>
```

If no recognized module system is present, access bundle contents via the global scope:

```html
<script type="text/javascript">
(function () {
    window.EPS;
})();
</script>
```

#### EPS

Difference between one and the smallest value greater than one that can be represented as a [double-precision floating-point number][ieee754].

```javascript
var bool = ( EPS === 2.220446049250313e-16 );
// returns true
```

</section>

<!-- /.usage -->

<section class="examples">

## Examples

<!-- eslint no-undef: "error" -->

```html
<!DOCTYPE html>
<html lang="en">
<body>
<script type="text/javascript" src="https://cdn.jsdelivr.net/gh/stdlib-js/math-base-special-abs@umd/browser.js"></script>
<script type="text/javascript" src="https://cdn.jsdelivr.net/gh/stdlib-js/math-base-special-max@umd/browser.js"></script>
<script type="text/javascript" src="https://cdn.jsdelivr.net/gh/stdlib-js/random-base-randu@umd/browser.js"></script>
<script type="text/javascript" src="https://cdn.jsdelivr.net/gh/stdlib-js/constants-float64-eps@umd/browser.js"></script>
<script type="text/javascript">
(function () {

var bool;
var a;
var b;
var i;

function isApprox( a, b ) {
    var delta;
    var tol;

    delta = abs( a - b );
    tol = EPS * max( abs( a ), abs( b ) );

    return ( delta <= tol );
}

for ( i = 0; i < 100; i++ ) {
    a = randu() * 10.0;
    b = a + (randu()*5.0e-15) - 2.5e-15;
    bool = isApprox( a, b );
    console.log( '%d %s approximately equal to %d. Delta: %d.', a, ( bool ) ? 'is' : 'is not', b, abs( a - b ) );
}

})();
</script>
</body>
</html>
```

</section>

<!-- /.examples -->

<!-- C interface documentation. -->



<!-- Section for related `stdlib` packages. Do not manually edit this section, as it is automatically populated. -->

<section class="related">

* * *

## See Also

-   <span class="package-name">[`@stdlib/constants-float32/eps`][@stdlib/constants/float32/eps]</span><span class="delimiter">: </span><span class="description">difference between one and the smallest value greater than one that can be represented as a single-precision floating-point number.</span>

</section>

<!-- /.related -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->


<section class="main-repo" >

* * *

## Notice

This package is part of [stdlib][stdlib], a standard library for JavaScript and Node.js, with an emphasis on numerical and scientific computing. The library provides a collection of robust, high performance libraries for mathematics, statistics, streams, utilities, and more.

For more information on the project, filing bug reports and feature requests, and guidance on how to develop [stdlib][stdlib], see the main project [repository][stdlib].

#### Community

[![Chat][chat-image]][chat-url]

---

## License

See [LICENSE][stdlib-license].


## Copyright

Copyright &copy; 2016-2023. The Stdlib [Authors][stdlib-authors].

</section>

<!-- /.stdlib -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="links">

[npm-image]: http://img.shields.io/npm/v/@stdlib/constants-float64-eps.svg
[npm-url]: https://npmjs.org/package/@stdlib/constants-float64-eps

[test-image]: https://github.com/stdlib-js/constants-float64-eps/actions/workflows/test.yml/badge.svg?branch=v0.1.1
[test-url]: https://github.com/stdlib-js/constants-float64-eps/actions/workflows/test.yml?query=branch:v0.1.1

[coverage-image]: https://img.shields.io/codecov/c/github/stdlib-js/constants-float64-eps/main.svg
[coverage-url]: https://codecov.io/github/stdlib-js/constants-float64-eps?branch=main

<!--

[dependencies-image]: https://img.shields.io/david/stdlib-js/constants-float64-eps.svg
[dependencies-url]: https://david-dm.org/stdlib-js/constants-float64-eps/main

-->

[chat-image]: https://img.shields.io/gitter/room/stdlib-js/stdlib.svg
[chat-url]: https://app.gitter.im/#/room/#stdlib-js_stdlib:gitter.im

[stdlib]: https://github.com/stdlib-js/stdlib

[stdlib-authors]: https://github.com/stdlib-js/stdlib/graphs/contributors

[umd]: https://github.com/umdjs/umd
[es-module]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules

[deno-url]: https://github.com/stdlib-js/constants-float64-eps/tree/deno
[umd-url]: https://github.com/stdlib-js/constants-float64-eps/tree/umd
[esm-url]: https://github.com/stdlib-js/constants-float64-eps/tree/esm
[branches-url]: https://github.com/stdlib-js/constants-float64-eps/blob/main/branches.md

[stdlib-license]: https://raw.githubusercontent.com/stdlib-js/constants-float64-eps/main/LICENSE

[ieee754]: https://en.wikipedia.org/wiki/IEEE_754-1985

[machine-epsilon]: https://en.wikipedia.org/wiki/Machine_epsilon

<!-- <related-links> -->

[@stdlib/constants/float32/eps]: https://github.com/stdlib-js/constants-float32-eps/tree/umd

<!-- </related-links> -->

</section>

<!-- /.links -->
