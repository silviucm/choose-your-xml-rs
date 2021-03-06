# Choose your XML

## Crates

| | |
| --- | --- |
| [xml-rs](https://crates.io/crates/xml-rs) | ![Version][xml-rs-version] ![CI][xml-rs-travis] |
| [quick-xml](https://crates.io/crates/quick-xml) | ![Version][quick-xml-version] ![CI][quick-xml-travis] |
| [xml5ever](https://crates.io/crates/xml5ever) | ![Version][xml5ever-version] ![CI][xml5ever-travis] |
| [sxd-document](https://crates.io/crates/sxd-document) | ![Version][sxd-document-version] ![CI][sxd-document-travis] |

[xml-rs-version]: https://img.shields.io/crates/v/xml-rs.svg
[quick-xml-version]: https://img.shields.io/crates/v/quick-xml.svg
[xml5ever-version]: https://img.shields.io/crates/v/xml5ever.svg
[sxd-document-version]: https://img.shields.io/crates/v/sxd-document.svg

[xml-rs-travis]: https://img.shields.io/travis/netvl/xml-rs.svg
[quick-xml-travis]: https://img.shields.io/travis/tafia/quick-xml.svg
[xml5ever-travis]: https://img.shields.io/travis/servo/html5ever.svg
[sxd-document-travis]: https://img.shields.io/travis/shepmaster/sxd-document.svg

## Features

|         Feature/Crate         |       xml-rs       |     quick-xml      |       xml5ever      |    sxd-document    |
| ----------------------------- | ------------------ | ------------------ | ------------------- | ------------------ |
| [Document type definition]    | No                 | No                 | Partial<sup>1</sup> | No                 |
| Namespaces                    | Yes                | Yes                | Yes                 | Yes                |
| [Numeric character reference] | Yes                | Yes                | Yes                 | Yes                |
| [XML entity reference]        | Yes                | Yes                | Yes                 | Yes                |
| [HTML entity reference]       | No                 | No                 | Yes                 | No                 |
| [DTD entity reference]        | No                 | No                 | No                  | No                 |
| `xml:space`                   | No                 | No                 | No                  | No                 |
| Non UTF-8 input               | No                 | Yes                | No                  | No                 |
| [XPath]                       | No                 | No                 | No                  | Extern<sup>2</sup> |
| [XQuery]                      | No                 | No                 | No                  | No                 |
| Streaming parser              | Yes                | Yes                | Yes                 | No                 |
| Pull parser                   | Yes                | Yes                | No                  | -                  |
| Push parser                   | No                 | No                 | Yes                 | -                  |
| DOM                           | Extern<sup>3</sup> | Extern<sup>4</sup> | Yes<sup>5</sup>     | Yes                |
| Error recovery                | No                 | No                 | Partial<sup>6</sup> | No                 |
| Writing                       | Yes                | Yes                | Yes                 | Yes                |

1. Only DTD without children. Also as stated in the [readme](https://github.com/servo/html5ever/blob/master/xml5ever/README.md#when-you-shouldnt-use-it).
2. Via [`sxd-xpath`](https://crates.io/crates/sxd-xpath) crate.
3. Via [`treexml`](https://crates.io/crates/treexml) or [`elementtree`](https://crates.io/crates/elementtree) crates.
4. Via [`minidom`](https://crates.io/crates/minidom) crate.
5. Using [`rcdom`](https://github.com/servo/html5ever/blob/master/markup5ever/rcdom.rs) module from the crate.
6. As stated in the [readme](https://github.com/servo/html5ever/blob/master/xml5ever/README.md#xml5ever).

[Document type definition]: https://en.wikipedia.org/wiki/Document_type_definition
[Numeric character reference]: https://en.wikipedia.org/wiki/Numeric_character_reference
[XPath]: https://en.wikipedia.org/wiki/XPath
[XQuery]: https://en.wikipedia.org/wiki/XQuery
[XML entity reference]: https://en.wikipedia.org/wiki/List_of_XML_and_HTML_character_entity_references#Predefined_entities_in_XML
[HTML entity reference]: https://en.wikipedia.org/wiki/List_of_XML_and_HTML_character_entity_references#Character_entity_references_in_HTML
[DTD entity reference]: https://en.wikipedia.org/wiki/List_of_XML_and_HTML_character_entity_references#Character_reference_overview

You can test features by yourself using corresponding example:

```bash
cargo run --example crate_name file_path

# example
cargo run --example quick_xml data/small.xml
```

## Performance

```
test quick_xml_large     ... bench:   1,935,674 ns/iter (+/- 2,550)
test quick_xml_medium    ... bench:     600,100 ns/iter (+/- 3,576)
test quick_xml_small     ... bench:       6,748 ns/iter (+/- 26)

test sxd_document_large  ... bench:      failed
test sxd_document_medium ... bench:   2,499,074 ns/iter (+/- 12,759)
test sxd_document_small  ... bench:      39,248 ns/iter (+/- 78)

test xml5ever_large      ... bench:   8,216,309 ns/iter (+/- 6,228)
test xml5ever_medium     ... bench:   7,305,346 ns/iter (+/- 10,139)
test xml5ever_small      ... bench:      43,917 ns/iter (+/- 63)

test xmlrs_large         ... bench:  26,470,342 ns/iter (+/- 34,884)
test xmlrs_medium        ... bench:  13,817,106 ns/iter (+/- 12,688)
test xmlrs_small         ... bench:      93,457 ns/iter (+/- 107)
```

You can run benchmarks by yourself using `cargo bench`.

\* Note that `sxd-document` generates a whole DOM.

## Contributing

Any suggestions and patches are welcome. Especially from crate authors.

## License

This repo is licensed under MIT license.
