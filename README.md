# Capsula

[![Join the chat at https://gitter.im/capsula-js/Lobby](https://badges.gitter.im/capsula-js/Lobby.svg)](https://gitter.im/capsula-js/Lobby?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

**Capsula** is a JavaScript library for building user interfaces and other event-driven software using highly reusable, flexible, and encapsulated software components called *capsules*. Capsula is executable both within the browser and node.js.

Capsula is a sort of dynamic, general-purpose, [object-oriented](https://en.wikipedia.org/wiki/Object-oriented_programming) "language" that accommodates many new and powerful concepts designed to handle complexity and favor abstraction, encapsulation, flexibility, and reuse. It also provides for both declarative and imperative programming styles which can be easily used in combination.

Among other concepts, Capsula exhibits concepts specifically dedicated to the domain of user interfaces. By default, Capsula supports building web UIs (relies on the DOM API), however this can be changed by extending it to work with any other JavaScript widget API.

It is quite usual for applications to communicate with third-party applications or systems based on the client-server (request-response) paradigm. Capsula helps here by setting the client code free of any physical details of communication, so that programmer's focus is only on what's essential.

Check the [documentation](https://solsoftware.github.io/capsula/) to make yourself familiar with all the concepts of Capsula library.

## Getting started

Install **Capsula** using npm.

```
npm i @solsoftware/capsula
```

At this point, Capsula comprises three modules: capsula (the core module), services, and html. More modules are coming soon.

### Using Capsula within your web browser

To start in a rather trivial way just take the following lines and put them into your web page:

```html
<script src="yourPathToCapsula/services.js"></script>
<script src="yourPathToCapsula/capsula.js"></script>
<script src="yourPathToCapsula/html.js"></script>
```

Otherwise, to require modules using RequireJS try:

```js
require(['capsula'], function (capsula) {
    ...
});
require(['html'], function (html) {
    ...
});
require(['services'], function (services) {
    ...
});
```

or all in one:

```js
requirejs(['services', 'capsula', 'html'], function (services, capsula, html) {
    ...
});
```

Now that you are ready, try the following "Hello world" examples:

```js
var C = capsula.defCapsule({ // new capsule class
        '> x': function () { // new input operation
            return 'Hello world!';
        }
    });
var c = new C(); // new capsule instance
console.log(c.x()); // Hello world!
```

To play with an existing DOM element:

```js
var bodyWrapper = new html.Element(document.body, ['click']);
bodyWrapper.click.target(function (e) {
    alert('Body clicked!');
});
```

### Using Capsula with Node.js

To require core capsula module and services module try:

```js
var capsula = require('@solsoftware/capsula');
var services = require('@solsoftware/capsula/dist/services');
```

Module html is missing here, since it depends on the DOM API; i.e. it does not really work server side.

## Sandbox

For a quick start let's run the Hello World application. Just copy the contents of the `sandbox` folder into the root folder of your web app and open the `index.html` file in your web browser. The source code for the "Hello world" page is in the `sandbox/scripts/main.js` file.

## Documentation

Documentation is available [here](https://solsoftware.github.io/capsula/).

## Contributing

Use [Github issues](https://github.com/solsoftware/capsula/issues) to report problems, suggest improvements, etc.

If you are willing to help further develop this project, please read the [our contribution guidelines](https://github.com/solsoftware/capsula/blob/master/CONTRIBUTING.md) file for all the details.

## Release History

Visit [Github releases](https://github.com/solsoftware/capsula/releases) to browse release history.

## Versioning

We use [semantic versioning](https://semver.org/).

## Maintainers

- [Zarko Mijailovic](mailto:zarko.mijailovic@sol.rs), SOL Software

## Code of Conduct
Please note that this project is released with a [Contributor Code of Conduct](https://github.com/solsoftware/capsula/blob/master/CODE_OF_CONDUCT.md). By participating in this project you agree to abide by its terms.

## Attributions

- Tests have been developed using Jasmine: [https://jasmine.github.io/index.html](https://jasmine.github.io/index.html)
- Documentation has been developed using JSDoc: [http://usejsdoc.org/](http://usejsdoc.org/)
- Drawings have been developed using draw.io: [https://www.draw.io/](https://www.draw.io/)

## License

Copyright (c) 2018 SOL Software. This software is licensed under the Apache-2.0 License.
