# SVG File Boilerplate

The simplest svg drawing that we can render and see looks something like this:

```xml
<?xml version="1.0" encoding="UTF-8" standalone="no"?>

<svg  
    version="1.1" 
    xmlns="http://www.w3.org/2000/svg">

    <!-- SVG Content -->
    <rect width="100" height="100" fill="red" />

</svg>
```

It will render to this a 300x150 -The default size of an SVG- drawing containing a red square:

<svg  
    version="1.1"
    xmlns="http://www.w3.org/2000/svg"
    style="outline: 1px dashed gray; "
    >
    <rect width="100" height="100" fill="red"  /> 
</svg>

There are several things to note here. The first is that we start with an XML declaration that marks the beginning of an XML document. It contains three important pieces of information:

`<?xml version="1.0"?>`: This specifies the XML version of the document. In this case, it's version 1.0, which is the most common version.

`encoding="UTF-8"?>`: This defines the character encoding used in the document. UTF-8 is a popular encoding that can represent a wide range of characters.

`standalone="no"?>`: This attribute indicates whether the XML document is standalone or not. A value of "no" means that the document may rely on an external Document Type Definition (DTD) for its complete definition.

`<svg ...>` defines the main SVG element. Here are its important attributes:

`version="1.1"`: specifies the SVG version as 1.1.

`xmlns="http://www.w3.org/2000/svg"`: defines the namespace for SVG elements. This namespace is essential for browsers to recognize the element as an SVG.

`style="outline: 1px dashed gray;"`: applies a CSS style to make easy to recognize the drawing borders.

`<rect ... />` defines a rectangle element.

## Using namespaces

A namespace is a string that can be defined using `xmlns` tag. the SVG namespace is `'http://www.w3.org/2000/svg'` and is declared to make the xml document cabable of mixing differnet namespaces like the MathML `'http://www.w3.org/1998/Math'` and Xlink `'http://www.w3.org/1999/xlink'`. 

The first namespace is the default namespace and it is applied to all the elements in the document. Unless a new declaration is used on the child elements. We can also redeclare the default namespace.

We can use a **prefix** to avoid this declaring and redeclaring the namespace. Because prefixing an element set its namespace but not its children.

```xml
<document xmlns="http://www.example.com/mySchema"
         xmlns:dc="http://purl.org/dc/elements/1.1/">
  <title>My Document Title</title>
  <dc:creator>John Doe</dc:creator>
  <dc:date>2024-03-28</dc:date>
  </document>
```

we can use a prefix to define the parameters not just elements.

```xml
<svg
  xmlns="http://www.w3.org/2000/svg"
  xmlns:xlink="http://www.w3.org/1999/xlink"
  >
 
  <script xlink:href="cool-script.js" type="text/javascript" />

</svg>
```

## Example SVG File

```xml
<?xml version="1.0" encoding="UTF-8" standalone="no"?>

<svg  version="1.1"

xmlns="http://www.w3.org/2000/svg"
xmlns:svg="http://www.w3.org/2000/svg"
xmlns:xlink="http://www.w3.org/1999/xlink"

xmlns:dc="http://purl.org/dc/elements/1.1/"
xmlns:cc="http://creativecommons.org/ns#"
xmlns:rdf="http://www.w3.org/1999/02/22-rdf-syntax-ns#"

width="300" height="150" viewBox="0 0 300 150"
style="outline: 1px dashed gray;"
>

    <rect width="100" height="100" fill="red" />

</svg>
```

You can add metadata as the last element in `<svg>`

```xml
  <metadata
     id="metadata1">
    <rdf:RDF>
      <cc:Work
         rdf:about="">
        <dc:creator>
          <cc:Agent>
            <dc:title>Yasser Muayed</dc:title>
          </cc:Agent>
        </dc:creator>
        <dc:title>An example svg drawing</dc:title>
        <dc:date>2024</dc:date>
        <dc:rights>
          <cc:Agent>
            <dc:title>creativecommons</dc:title>
          </cc:Agent>
        </dc:rights>
        <cc:license
           rdf:resource="http://creativecommons.org/licenses/by-nc-nd/4.0/" />
        <dc:publisher>
          <cc:Agent>
            <dc:title>Yasser Muayed</dc:title>
          </cc:Agent>
        </dc:publisher>
        <dc:identifier>https://yassermuayed.github.io/notes/svg_elements_catagories.html</dc:identifier>
        <dc:source>https://yassermuayed.github.io/notes</dc:source>
        <dc:relation>https://yassermuayed.github.io</dc:relation>
        <dc:language>English</dc:language>
        <dc:subject>
          <rdf:Bag>
            <rdf:li>Example</rdf:li>
          </rdf:Bag>
        </dc:subject>
        <dc:coverage>wtf</dc:coverage>
        <dc:description>An example svg drawing that shows basic usage</dc:description>
        <dc:contributor>
          <cc:Agent>
            <dc:title>Yasser Muayed</dc:title>
          </cc:Agent>
        </dc:contributor>
      </cc:Work>
      <cc:License
         rdf:about="http://creativecommons.org/licenses/by-nc-nd/4.0/">
        <cc:permits
           rdf:resource="http://creativecommons.org/ns#Reproduction" />
        <cc:permits
           rdf:resource="http://creativecommons.org/ns#Distribution" />
        <cc:requires
           rdf:resource="http://creativecommons.org/ns#Notice" />
        <cc:requires
           rdf:resource="http://creativecommons.org/ns#Attribution" />
        <cc:prohibits
           rdf:resource="http://creativecommons.org/ns#CommercialUse" />
      </cc:License>
    </rdf:RDF>
  </metadata>
  ```