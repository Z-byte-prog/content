---
title: fit-content()
slug: Web/CSS/fit-content_function
page-type: css-function
browser-compat:
  - css.properties.grid-template-columns.fit-content
  - css.properties.width.fit-content_function
sidebar: cssref
---

The **`fit-content()`** [CSS](/en-US/docs/Web/CSS) [function](/en-US/docs/Web/CSS/CSS_Values_and_Units/CSS_Value_Functions) clamps a given size to an available size according to the formula `min(maximum size, max(minimum size, argument))`.

{{InteractiveExample("CSS Demo: fit-content()")}}

```css interactive-example-choice
grid-template-columns: fit-content(8ch) fit-content(8ch) 1fr;
```

```css interactive-example-choice
grid-template-columns: fit-content(100px) fit-content(100px) 1fr;
```

```css interactive-example-choice
grid-template-columns: fit-content(40%) fit-content(40%) 1fr;
```

```html interactive-example
<section class="default-example" id="default-example">
  <div class="example-container">
    <div class="transition-all" id="example-element">
      <div>One. This column has more text in it.</div>
      <div>Two</div>
      <div>Three</div>
      <div>Four</div>
      <div>Five</div>
    </div>
  </div>
</section>
```

```css interactive-example
#example-element {
  border: 1px solid #c5c5c5;
  display: grid;
  grid-gap: 10px;
  width: 250px;
}

#example-element > div {
  background-color: rgb(0 0 255 / 0.2);
  border: 3px solid blue;
  text-align: left;
}
```

The function can be used as a track size in [CSS grid](/en-US/docs/Web/CSS/CSS_grid_layout) properties, where the maximum size is defined by `max-content` and the minimum size by `auto`, which is calculated similar to `auto` (i.e., [`minmax(auto, max-content)`](/en-US/docs/Web/CSS/minmax)), except that the track size is clamped at _argument_ if it is greater than the `auto` minimum.

See the {{cssxref("grid-template-columns")}} page for more information on the `max-content` and `auto` keywords.

The `fit-content()` function can also be used as laid out box size for {{cssxref("width")}}, {{cssxref("height")}}, {{cssxref("min-width")}}, {{cssxref("min-height")}}, {{cssxref("max-width")}} and {{cssxref("max-height")}}, where the maximum and minimum sizes refer to the content size.

## Syntax

```css
/* <length> values */
fit-content(200px)
fit-content(5cm)
fit-content(30vw)
fit-content(100ch)

/* <percentage> value */
fit-content(40%)
```

### Values

- {{cssxref("&lt;length&gt;")}}
  - : An absolute length.
- {{cssxref("&lt;percentage&gt;")}}
  - : A percentage relative to the available space in the given axis.

    In grid properties it is relative to the inline size of the grid container in column tracks and to the block size of the grid container for row tracks. Otherwise it is relative to the available inline size or block size of the laid out box depending on the writing mode.

## Formal syntax

{{CSSSyntax("fit-content")}}

## Examples

### Sizing grid columns with fit-content

#### HTML

```html
<div id="container">
  <div>Item as wide as the content.</div>
  <div>
    Item with more text in it. Because the contents of it are wider than the
    maximum width, it is clamped at 300 pixels.
  </div>
  <div>Flexible item</div>
</div>
```

#### CSS

```css
#container {
  display: grid;
  grid-template-columns: fit-content(300px) fit-content(300px) 1fr;
  grid-gap: 5px;
  box-sizing: border-box;
  height: 200px;
  width: 100%;
  background-color: #8cffa0;
  padding: 10px;
}

#container > div {
  background-color: #8ca0ff;
  padding: 5px;
}
```

#### Result

{{EmbedLiveSample("Sizing_grid_columns_with_fit-content", "100%", 200)}}

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}

## See also

- {{cssxref("min-content")}} keyterm
- {{cssxref("max-content")}} keyterm
- [CSS box sizing](/en-US/docs/Web/CSS/CSS_box_sizing) module
- {{cssxref("grid-template")}}
- {{cssxref("grid-template-rows")}}
- {{cssxref("grid-template-columns")}}
- {{cssxref("grid-template-areas")}}
- {{cssxref("grid-auto-columns")}}
- {{cssxref("grid-auto-rows")}}
- {{cssxref("grid-auto-flow")}}
- [Line-based placement with CSS grid](/en-US/docs/Web/CSS/CSS_grid_layout/Grid_layout_using_line-based_placement)
- [Grid template areas: grid definition shorthands](/en-US/docs/Web/CSS/CSS_grid_layout/Grid_template_areas#grid_definition_shorthands)
