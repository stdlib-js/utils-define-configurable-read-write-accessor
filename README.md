<!--

@license Apache-2.0

Copyright (c) 2019 The Stdlib Authors.

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

# Configurable Read-Write Accessor

[![NPM version][npm-image]][npm-url] [![Build Status][test-image]][test-url] [![Coverage Status][coverage-image]][coverage-url] <!-- [![dependencies][dependencies-image]][dependencies-url] -->

> [Define][@stdlib/utils/define-property] a configurable **read-write** accessor.

<section class="installation">

## Installation

```bash
npm install @stdlib/utils-define-configurable-read-write-accessor
```

Alternatively,

-   To load the package in a website via a `script` tag without installation and bundlers, use the [ES Module][es-module] available on the [`esm` branch][esm-url].
-   If you are using Deno, visit the [`deno` branch][deno-url].
-   For use in Observable, or in browser/node environments, use the [Universal Module Definition (UMD)][umd] build available on the [`umd` branch][umd-url].

</section>

<section class="usage">

## Usage

<!-- eslint-disable id-length -->

```javascript
var setConfigurableReadWriteAccessor = require( '@stdlib/utils-define-configurable-read-write-accessor' );
```

#### setConfigurableReadWriteAccessor( obj, prop, getter, setter )

[Defines][@stdlib/utils/define-property] a configurable **read-write** accessor.

<!-- eslint-disable id-length -->

```javascript
var word = 'bar';
var obj = {};

function getter() {
    return word + ' foo';
}

function setter( v ) {
    word = v;
}

setConfigurableReadWriteAccessor( obj, 'foo', getter, setter );

var v = obj.foo;
// returns 'bar foo'

obj.foo = 'beep';

v = obj.foo;
// returns 'beep foo'
```

</section>

<!-- /.usage -->

<section class="notes">

## Notes

-   Configurable read-write accessors are **enumerable**.

</section>

<!-- /.notes -->

<section class="examples">

## Examples

<!-- eslint-disable id-length -->

<!-- eslint no-undef: "error" -->

```javascript
var setConfigurableReadWriteAccessor = require( '@stdlib/utils-define-configurable-read-write-accessor' );

function Foo( name ) {
    if ( !(this instanceof Foo) ) {
        return new Foo( name );
    }
    setConfigurableReadWriteAccessor( this, 'name', getName, setName );
    return this;

    function getName() {
        return 'Hello, ' + name;
    }

    function setName( v ) {
        name = v;
    }
}

var foo = new Foo( 'Grace' );
console.log( foo.name );

foo.name = 'Ada';
console.log( foo.name );
```

</section>

<!-- /.examples -->

<!-- Section for related `stdlib` packages. Do not manually edit this section, as it is automatically populated. -->

<section class="related">

* * *

## See Also

-   <span class="package-name">[`@stdlib/utils/define-configurable-read-only-property`][@stdlib/utils/define-configurable-read-only-property]</span><span class="delimiter">: </span><span class="description">define a configurable read-only property.</span>
-   <span class="package-name">[`@stdlib/utils/define-configurable-read-only-accessor`][@stdlib/utils/define-configurable-read-only-accessor]</span><span class="delimiter">: </span><span class="description">define a configurable read-only accessor.</span>
-   <span class="package-name">[`@stdlib/utils/define-configurable-write-only-accessor`][@stdlib/utils/define-configurable-write-only-accessor]</span><span class="delimiter">: </span><span class="description">define a configurable write-only accessor.</span>
-   <span class="package-name">[`@stdlib/utils/define-property`][@stdlib/utils/define-property]</span><span class="delimiter">: </span><span class="description">define (or modify) an object property.</span>
-   <span class="package-name">[`@stdlib/utils/define-read-write-accessor`][@stdlib/utils/define-read-write-accessor]</span><span class="delimiter">: </span><span class="description">define a read-write accessor.</span>

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

Copyright &copy; 2016-2021. The Stdlib [Authors][stdlib-authors].

</section>

<!-- /.stdlib -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="links">

[npm-image]: http://img.shields.io/npm/v/@stdlib/utils-define-configurable-read-write-accessor.svg
[npm-url]: https://npmjs.org/package/@stdlib/utils-define-configurable-read-write-accessor

[test-image]: https://github.com/stdlib-js/utils-define-configurable-read-write-accessor/actions/workflows/test.yml/badge.svg
[test-url]: https://github.com/stdlib-js/utils-define-configurable-read-write-accessor/actions/workflows/test.yml

[coverage-image]: https://img.shields.io/codecov/c/github/stdlib-js/utils-define-configurable-read-write-accessor/main.svg
[coverage-url]: https://codecov.io/github/stdlib-js/utils-define-configurable-read-write-accessor?branch=main

<!--

[dependencies-image]: https://img.shields.io/david/stdlib-js/utils-define-configurable-read-write-accessor.svg
[dependencies-url]: https://david-dm.org/stdlib-js/utils-define-configurable-read-write-accessor/main

-->

[umd]: https://github.com/umdjs/umd
[es-module]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules

[deno-url]: https://github.com/stdlib-js/utils-define-configurable-read-write-accessor/tree/deno
[umd-url]: https://github.com/stdlib-js/utils-define-configurable-read-write-accessor/tree/umd
[esm-url]: https://github.com/stdlib-js/utils-define-configurable-read-write-accessor/tree/esm

[chat-image]: https://img.shields.io/gitter/room/stdlib-js/stdlib.svg
[chat-url]: https://gitter.im/stdlib-js/stdlib/

[stdlib]: https://github.com/stdlib-js/stdlib

[stdlib-authors]: https://github.com/stdlib-js/stdlib/graphs/contributors

[stdlib-license]: https://raw.githubusercontent.com/stdlib-js/utils-define-configurable-read-write-accessor/main/LICENSE

[@stdlib/utils/define-property]: https://github.com/stdlib-js/utils-define-property

<!-- <related-links> -->

[@stdlib/utils/define-configurable-read-only-property]: https://github.com/stdlib-js/utils-define-configurable-read-only-property

[@stdlib/utils/define-configurable-read-only-accessor]: https://github.com/stdlib-js/utils-define-configurable-read-only-accessor

[@stdlib/utils/define-configurable-write-only-accessor]: https://github.com/stdlib-js/utils-define-configurable-write-only-accessor

[@stdlib/utils/define-property]: https://github.com/stdlib-js/utils-define-property

[@stdlib/utils/define-read-write-accessor]: https://github.com/stdlib-js/utils-define-read-write-accessor

<!-- </related-links> -->

</section>

<!-- /.links -->
