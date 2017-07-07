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

| Feature/Crate                 | xml-rs           | quick-xml        | xml5ever         | sxd-document     |
| ----------------------------- | ---------------- | ---------------- | ---------------- | ---------------- |
| [Document type definition]    | No               | No               | [Partial][1:3]   | Partial          |
| Namespaces                    | Yes              | Yes              | ?                | Yes              |
| [Numeric character reference] | Yes              | Yes              | Yes              | Yes              |
| [XML entity reference]        | Yes              | Yes              | Yes              | Yes              |
| [HTML entity reference]       | No               | No               | Yes              | No               |
| [DTD entity reference]        | No               | No               | No               | No               |
| `xml:space`                   | No               | No               | No               | No               |
| Non UTF-8 input               | No               | No               | Yes              | No               |
| [XPath]                       | No               | No               | No               | [Yes][7:4]       |
| [XQuery]                      | No               | No               | No               | No               |
| Event parser                  | Yes              | Yes              | Yes              | No               |
| Push parser                   | No               | No               | Yes              | No               |
| Error recovery                | No               | No               | Partial          | No               |
| DOM                           | No               | No               | [Yes][11:3]      | Yes              |
| Writing                       | Yes              | Yes              | Yes              | Yes              |

[Document type definition]: https://en.wikipedia.org/wiki/Document_type_definition
[Numeric character reference]: https://en.wikipedia.org/wiki/Numeric_character_reference
[XPath]: https://en.wikipedia.org/wiki/XPath
[XQuery]: https://en.wikipedia.org/wiki/XQuery
[XML entity reference]: https://en.wikipedia.org/wiki/List_of_XML_and_HTML_character_entity_references#Predefined_entities_in_XML
[HTML entity reference]: https://en.wikipedia.org/wiki/List_of_XML_and_HTML_character_entity_references#Character_entity_references_in_HTML
[DTD entity reference]: https://en.wikipedia.org/wiki/List_of_XML_and_HTML_character_entity_references#Character_reference_overview

[1:3]: https://github.com/servo/html5ever/blob/master/xml5ever/README.md#when-you-shouldnt-use-it
[11:3]: https://github.com/servo/html5ever/blob/master/markup5ever/rcdom.rs
[7:4]: https://crates.io/crates/sxd-xpath

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
