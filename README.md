# Immediate-mode DOM tools

Lightweight tooling around `document.createElement()`.
Designed to be embedded piecewise in self-contained Web Components.


## API

### [Immediate DOM API](docs/imm_dom.md):

```javascript
imm_html.article({class: 'awesome'},
  imm_html.h3('my demo title'),
  'some body text')

// or

tag('article', {class: 'awesome'},
  tag('h3', 'my demo title'),
  'some body text')
```

Inspired by:
- [hyperscript](https://github.com/hyperhype/hyperscript#readme)
- [superfine](https://github.com/jorgebucaran/superfine#readme)
- [crel](https://github.com/KoryNunn/crel#readme)
- [jaml](https://github.com/edspencer/jaml#readme)
- [jsonml](http://www.jsonml.org)
- [hast](https://github.com/syntax-tree/hast#readme)


### [Immediate Template API](docs/imm_tmpl.md):

```javascript
imm_tmpl`
  <article ${ {class: 'awesome'} }>
    <h3>${ 'my demo title' }</h3>
    ${ 'some body text' }
  </article>`
```

Inspired by:
- [uce](https://github.com/WebReflection/uce#readme)
  and [uhtml](https://github.com/WebReflection/uhtml#readme)


### [Immediate Utility API](docs/imm_utils.md):


## Sizes

To be embedded in each web component custom elemenet,
the individual pieces must be small.

The entire library is ~ **2000 bytes** minified; ~ **1000 brotli**.
However, the library is _designed to include only the parts actually used_.

  - `imm_tmpl` alone costs ~ 1100 bytes minified; ~ 600 brotli.
  - `imm_dom` costs ~ 600 bytes minified; ~ 350 brotli.

Perfect for paring with a tree-shaking tool like [rollup][]
See auto-generated [compressed size report](./docs/compressed.md).

| module          |  bytes |    min | gziped | brotli |
|:----------------|-------:|-------:|-------:|-------:|
| `index`         |   4622 |   1933 |   1062 |    956 |
| `imm_tmpl`      |   3098 |   1092 |    672 |    574 |
| `imm_dom`       |   1142 |    589 |    391 |    313 |
| `imm_raf`       |    567 |    292 |    236 |    194 |


## License

[BSD 2-clause](LICENSE)


 [rollup]: https://rollupjs.org
