# SVG Elements Catagories

What is available for use in an svg document?

So far I have 63 SVG elements listed below. We can group theme into catagories depending on their function

1. Document and metadata
2. Basic Shapes
3. The `<path>` Element
4. Text and Typography
5. Grouping and Containers
6. Gradient and Pattern Elements
7. Filtering and Masking Elements
8. Animation Elements
9. Interactivity and Other Elements

## Document level tags and metadata

1. `<desc>`
2. `<title>`
3. `<metadata>`
4. `<svg>`

## Basic shapes

1. `<rect>`
2. `<circle>`
3. `<ellipse>`
4. `<line>`
5. `<polyline>`
6. `<polygon>`

## The <path> element

1. `<path>`

## Text and Typography

1. `<text>`
2. `<tspan>`
3. `<textPath>`

Example of using `<textPath>` to create curved texted.

![SVG Curved Text Follosing a path with textPath element](https://wolthera.info/wp-content/uploads/2022/10/image-20.png)

## Grouping Elements

1. `<g>`
2. `<defs>`
3. `<use>`
4. `<symbol>`

Technically, `<defs>` itself isn't used to render anything visually. It defines elements for later use with `<use>` and `<symbol>`.

## Gradient

1. `<linearGradient>`
2. `<radialGradient>`
3. `<stop>`

```xml
<svg width="200" height="100">
  <rect width="200" height="100" fill="url(#linearGradient)" />
  <linearGradient id="linearGradient">
    <stop offset="0%" stop-color="blue" />
    <stop offset="100%" stop-color="yellow" />
  </linearGradient>
</svg>
```

```xml
<svg width="200" height="200">
  <circle cx="100" cy="100" r="80" fill="url(#radialGradient)" />
  <radialGradient id="radialGradient">
    <stop offset="0%" stop-color="red" />
    <stop offset="70%" stop-color="orange" />
    <stop offset="100%" stop-color="yellow" />
  </radialGradient>
</svg>
```

In `<stop>` we can use other values besides percentages, like pixels (20px).

## Filtering and Masking

1. `<mask>`
2. `<filter>`
3. `<feDropShadow>`
4. `<feComponentTransfer>`
5. `<feFuncA>`
6. `<feFuncB>`
7. `<feFuncG>`
8. `<feFuncR>`
9. `<feFlood>`
10. `<feBlend>`
11. `<feOffset>`
12. `<feImage>`
13. `<feMerge>`
14. `<feMergeNode>`
15. `<feMorphology>`
16. `<feGaussianBlur>`
17. `<feColorMatrix>`
18. `<feComposite>`
19. `<feConvolveMatrix>`
20. `<feDiffuseLighting>`
21. `<feSpecularLighting>`
22. `<feSpotLight>`
23. `<feTile>`
24. `<feTurbulence>`
25. `<fePointLight>`
26. `<feDisplacementMap>`
27. `<feDistantLight>`

![SVG Filters](https://codrops-1f606.kxcdn.com/codrops/wp-content/uploads/2019/01/Group-1.png)

## Animation Elements

1. `<animate>`
2. `<animateMotion>`
3. `<mpath>`
4. `<animateTransform>`
5. `<image>`
6. `<set>`

![SVG Animations Example](https://cdn.svgator.com/images/2022/06/background-svg-patterns.gif)

## interactivity and other

1. `<a>`
2. `<foreignObject>`
3. `<script>`
4. `<clipPath>`
5. `<marker>`
6. `<pattern>`
7. `<style>`
8. `<switch>`
9. `<view>`
