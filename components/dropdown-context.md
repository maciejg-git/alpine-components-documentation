---
layout: "layouts/container.liquid"
tags: component
name: Dropdown context
examples: {
    dropdownContextSimple: [
        {
            label: "Template",
            file: "examples/dropdown-context-simple.liquid",
            language: "html",
        },
    ],
}
props: [
    {
        name: "autoClose",
        type: ["Boolean"],
        default: "true",
        description: "If `true` menu is closed after click on any element inside.",
    },
]
floatingOptions: [
    {
        name: "placement",
        type: ["String"],
        default: "bottom-start",
        description: "Initial placement of dropdown content. See floatingUI documentation for valid values.",
    },
    {
        name: "offsetX",
        type: ["Number"],
        default: "0",
        description: "Offset of dropdown relative to reference element.",
    },
    {
        name: "offsetY",
        type: ["Number"],
        default: "0",
        description: "Offset of dropdown relative to reference element.",
    },
    {
        name: "flip",
        type: ["Boolean"],
        default: "false",
        description: "Allows fliping of the dropdown to the opposite placement if outside of current view.",
    },
    {
        name: "autoPlacement",
        type: ["Boolean"],
        default: "false",
        description: "Automatically calculates best placement for the floating element.",
    },
    {
        name: "inline",
        type: ["Boolean"],
        default: "false",
        description: "",
    },
]
---
## Dropdown context

{% render "example.liquid" example: "examples/dropdown-context-simple.liquid", tabs: examples.dropdownContextSimple %}

### Usage

To use this component simply copy and paste minimal template or any template from the examples below.

The data for the component is provided by the `dropdownContext` function in the `x-data` directive. This function takes two `object` arguments: the props and floatingUI options.

```javascript
dropdownContext({
    autoClose: Boolean,
},
{
    placement: String,
    offsetX: Number,
    offsetY: Number,
    flip: Boolean,
    autoPlacement: Boolean,
    inline: Boolean,
})
```

{% render "reference.liquid" props: props %}
{% render "reference.liquid" props: floatingOptions %}

To show context menu simply dispatch open-contextmenu event. The data in the event should be an object with following properties:
- id of the context menu to show
- context data
- event to calculate position of the context menu
