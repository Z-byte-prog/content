---
title: "HTML attribute: readonly"
short-title: readonly
slug: Web/HTML/Reference/Attributes/readonly
page-type: html-attribute
browser-compat:
  - html.elements.input.readonly
  - html.elements.textarea.readonly
sidebar: htmlsidebar
---

The Boolean **`readonly`** attribute, when present, makes the element not mutable, meaning the user can not edit the control.

{{InteractiveExample("HTML Demo: readonly", "tabbed-shorter")}}

```html interactive-example
<label for="firstName">First Name:</label>
<input id="firstName" name="firstName" type="text" value="Adam" />

<label for="age">Age:</label>
<input id="age" name="age" type="number" value="42" readonly />

<label for="hobbies">Hobbies:</label>
<textarea id="hobbies" name="hobbies" readonly>Baseball</textarea>
```

```css interactive-example
label {
  display: block;
  margin-top: 1em;
}

input:read-only,
textarea:read-only {
  background-color: silver;
}
```

## Overview

If the `readonly` attribute is specified on an input element, because the user can not edit the input, the element does not participate in constraint validation.

The `readonly` attribute is supported by textual form controls, including:

- {{HTMLElement("input")}} elements of type:
  - `{{HTMLElement("input/text","text")}}`
  - `{{HTMLElement("input/search","search")}}`
  - `{{HTMLElement("input/tel","tel")}}`
  - `{{HTMLElement("input/url","url")}}`
  - `{{HTMLElement("input/email","email")}}`
  - `{{HTMLElement("input/password","password")}}`
  - `{{HTMLElement("input/date","date")}}`
  - `{{HTMLElement("input/month","month")}}`
  - `{{HTMLElement("input/week","week")}}`
  - `{{HTMLElement("input/time","time")}}`
  - `{{HTMLElement("input/datetime-local","datetime-local")}}`
  - `{{HTMLElement("input/number","number")}}`
- {{HTMLElement("textarea")}}

The attribute is not relevant to all other elements, including {{HTMLElement("select")}} and {{HTMLElement("button")}}. It also does not apply to non-textual input elements, including:

- `{{HTMLElement("input/hidden","hidden")}}`
- `{{HTMLElement("input/range","range")}}`
- `{{HTMLElement("input/color","color")}}`
- `{{HTMLElement("input/checkbox","checkbox")}}`
- `{{HTMLElement("input/radio","radio")}}`
- `{{HTMLElement("input/file","file")}}`
- `{{HTMLElement("input/submit","submit")}}`
- `{{HTMLElement("input/image","image")}}`
- `{{HTMLElement("input/reset","reset")}}`
- `{{HTMLElement("input/button","button")}}`

Inputs that support the `readonly` attribute but don't have the attribute set match the {{cssxref(":read-write")}} pseudo-class. All other elements match the {{cssxref(":read-only")}} pseudo-class.

### Attribute interactions

The difference between [`disabled`](/en-US/docs/Web/HTML/Reference/Attributes/disabled) and `readonly` is that read-only controls can still function and are still focusable, whereas disabled controls can not receive focus and are not submitted with the form and generally do not function as controls until they are enabled.

Because a read-only field cannot have its value changed by a user interaction, [`required`](/en-US/docs/Web/HTML/Reference/Attributes/required) does not have any effect on inputs with the `readonly` attribute also specified.

The only way to modify dynamically the value of the readonly attribute is through a script.

> [!NOTE]
> The `required` attribute is not permitted on inputs with the `readonly` attribute specified.

### Usability

Browsers display the `readonly` attribute.

### Constraint validation

If the element is read-only, then the element's value can not be updated by the user, and does not participate in constraint validation.

## Example

### HTML

```html
<div class="group">
  <input type="text" value="Some value" readonly="readonly" id="text" />
  <label for="text">Text box</label>
</div>
<div class="group">
  <input type="date" value="2020-01-01" readonly="readonly" id="date" />
  <label for="date">Date</label>
</div>
<div class="group">
  <input type="email" value="Some value" readonly="readonly" id="email" />
  <label for="email">Email</label>
</div>
<div class="group">
  <input type="password" value="Some value" readonly="readonly" id="pwd" />
  <label for="pwd">Password</label>
</div>
<div class="group">
  <textarea readonly="readonly" id="ta">Some value</textarea>
  <label for="ta">Message</label>
</div>
```

### Result

{{EmbedLiveSample('Example')}}

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}

## See also

- {{cssxref(':read-only')}} and {{cssxref(':read-write')}}
- {{htmlelement('input')}}
- {{htmlelement('select')}}
