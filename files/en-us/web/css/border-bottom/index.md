---
title: border-bottom
slug: Web/CSS/border-bottom
page-type: css-shorthand-property
browser-compat: css.properties.border-bottom
sidebar: cssref
---

The **`border-bottom`** [shorthand](/en-US/docs/Web/CSS/CSS_cascade/Shorthand_properties) [CSS](/en-US/docs/Web/CSS) property sets an element's bottom [border](/en-US/docs/Web/CSS/border). It sets the values of {{cssxref("border-bottom-width")}}, {{cssxref("border-bottom-style")}} and {{cssxref("border-bottom-color")}}.

{{InteractiveExample("CSS Demo: border-bottom")}}

```css interactive-example-choice
border-bottom: solid;
```

```css interactive-example-choice
border-bottom: dashed red;
```

```css interactive-example-choice
border-bottom: 1rem solid;
```

```css interactive-example-choice
border-bottom: thick double #32a1ce;
```

```css interactive-example-choice
border-bottom: 4mm ridge rgb(211 220 50 / 0.6);
```

```html interactive-example
<section class="default-example" id="default-example">
  <div class="transition-all" id="example-element">
    This is a box with a border around it.
  </div>
</section>
```

```css interactive-example
#example-element {
  background-color: #eee;
  color: #8b008b;
  padding: 0.75em;
  width: 80%;
  height: 100px;
}
```

As with all shorthand properties, `border-bottom` always sets the values of all of the properties that it can set, even if they are not specified. It sets those that are not specified to their default values. Consider the following code:

```css
border-bottom-style: dotted;
border-bottom: thick green;
```

It is actually the same as this one:

```css
border-bottom-style: dotted;
border-bottom: none thick green;
```

The value of {{cssxref("border-bottom-style")}} given before `border-bottom` is ignored. Since the default value of {{cssxref("border-bottom-style")}} is `none`, not specifying the `border-style` part results in no border.

## Constituent properties

This property is a shorthand for the following CSS properties:

- {{cssxref("border-bottom-color")}}
- {{cssxref("border-bottom-style")}}
- {{cssxref("border-bottom-width")}}

## Syntax

```css
border-bottom: 1px;
border-bottom: 2px dotted;
border-bottom: medium dashed blue;

/* Global values */
border-bottom: inherit;
border-bottom: initial;
border-bottom: revert;
border-bottom: revert-layer;
border-bottom: unset;
```

The three values of the shorthand property can be specified in any order, and one or two of them may be omitted.

### Values

- `<br-width>`
  - : See {{cssxref("border-bottom-width")}}.
- `<br-style>`
  - : See {{cssxref("border-bottom-style")}}.
- {{cssxref("&lt;color&gt;")}}
  - : See {{cssxref("border-bottom-color")}}.

## Formal definition

{{CSSInfo}}

## Formal syntax

{{csssyntax}}

## Examples

### Applying a bottom border

#### HTML

```html
<div>This box has a border on the bottom side.</div>
```

#### CSS

```css
div {
  border-bottom: 4px dashed blue;
  background-color: gold;
  height: 100px;
  width: 100px;
  font-weight: bold;
  text-align: center;
}
```

#### Results

{{EmbedLiveSample('Applying_a_bottom_border')}}

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}

## See also

- {{cssxref("border")}}
- {{cssxref("border-block")}}
- {{cssxref("outline")}}
