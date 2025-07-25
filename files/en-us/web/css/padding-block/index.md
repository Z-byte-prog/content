---
title: padding-block
slug: Web/CSS/padding-block
page-type: css-shorthand-property
browser-compat: css.properties.padding-block
sidebar: cssref
---

The **`padding-block`** [CSS](/en-US/docs/Web/CSS) [shorthand property](/en-US/docs/Web/CSS/CSS_cascade/Shorthand_properties) defines the logical block start and end padding of an element, which maps to physical padding properties depending on the element's writing mode, directionality, and text orientation.

{{InteractiveExample("CSS Demo: padding-block")}}

```css interactive-example-choice
padding-block: 10px 20px;
writing-mode: horizontal-tb;
```

```css interactive-example-choice
padding-block: 20px 40px;
writing-mode: vertical-rl;
```

```css interactive-example-choice
padding-block: 5% 10%;
writing-mode: horizontal-tb;
```

```css interactive-example-choice
padding-block: 2em 4em;
writing-mode: vertical-lr;
```

```html interactive-example
<section id="default-example">
  <div class="transition-all" id="example-element">
    <div class="box">
      Far out in the uncharted backwaters of the unfashionable end of the
      western spiral arm of the Galaxy lies a small unregarded yellow sun.
    </div>
  </div>
</section>
```

```css interactive-example
#example-element {
  border: 10px solid #ffc129;
  overflow: hidden;
  text-align: left;
}

.box {
  border: dashed 1px;
  unicode-bidi: bidi-override;
}
```

## Constituent properties

This property is a shorthand for the following CSS properties:

- {{cssxref("padding-block-start")}}
- {{cssxref("padding-block-end")}}

## Syntax

```css
/* <length> values */
padding-block: 10px 20px; /* An absolute length */
padding-block: 1em 2em; /* relative to the text size */
padding-block: 10px; /* sets both start and end values */

/* <percentage> values */
padding-block: 5% 2%; /* relative to the nearest block container's width */

/* Global values */
padding-block: inherit;
padding-block: initial;
padding-block: revert;
padding-block: revert-layer;
padding-block: unset;
```

The `padding-block` property may be specified with one or two values. If one value is given, it is used as the value for both {{cssxref("padding-block-start")}} and {{cssxref("padding-block-end")}}. If two values are given, the first is used for {{cssxref("padding-block-start")}} and the second for {{cssxref("padding-block-end")}}.

### Values

The `padding-block` property takes the same values as the {{cssxref("padding-left")}} property.

## Description

The padding values specified by `padding-block` can be equivalent to the {{cssxref("padding-top")}} and {{cssxref("padding-bottom")}} properties or the {{cssxref("padding-right")}} and {{cssxref("padding-left")}} properties, depending on the values defined for {{cssxref("writing-mode")}}, {{cssxref("direction")}}, and {{cssxref("text-orientation")}}.

## Formal definition

{{cssinfo}}

## Formal syntax

{{csssyntax}}

## Examples

### Setting block padding for vertical text

#### HTML

```html
<div>
  <p class="exampleText">Example text</p>
</div>
```

#### CSS

```css
div {
  background-color: yellow;
  width: 120px;
  height: 120px;
}

.exampleText {
  writing-mode: vertical-rl;
  padding-block: 20px 40px;
  background-color: #c8c800;
}
```

#### Result

{{EmbedLiveSample("Setting_block_padding_for_vertical_text", 140, 140)}}

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}

## See also

- [CSS Logical Properties and Values](/en-US/docs/Web/CSS/CSS_logical_properties_and_values)
- The mapped physical properties: {{cssxref("padding-top")}}, {{cssxref("padding-right")}}, {{cssxref("padding-bottom")}}, and {{cssxref("padding-left")}}
- {{cssxref("writing-mode")}}, {{cssxref("direction")}}, {{cssxref("text-orientation")}}
