# XSD1.1 Transformations

This is a little collection of XSL Transformations for XML Schemas of the new [1.1 standard](http://www.w3.org/TR/xmlschema11-1/). Its aim is to remove or replace XSD 1.1 elements to get a valid XSD 1.0 file. This can be useful if you want to use tools which don't support the new 1.1 standard yet or simply get a faster XSD validation by removing all assertions.

## Usage

As of yet there are only simple stylesheets, so you can take any XSLT processor you want, e.g. Apache Xalan:

```
xalan -in your-v1.1.xsd -xsl remove-asserts/remove-asserts.xsl -out generated-v1.0.xsd
```

## Stylesheets

* **remove-asserts**: Removes all `xs:assert` elements. Resulting XSD will be syntactically correct but maybe not semantically any more.
* **remove-assertions**: Removes all `xs:assertion` elements. Some `simpleType` will lose their restrictions.

## Todo

* Replace `xs:alternative` by the actually used type of the XML.
