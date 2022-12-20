---
layout: post
title: Accessibility in Blazor Mention Component | Syncfusion
description: Checkout and learn here all about accessibility in Syncfusion Blazor Mention component and much more details.  
platform: Blazor
control: Mention
documentation: ug
---

# Accessibility in Blazor Mention Component

Web accessibility makes web contents and applications more accessible to people with disabilities. The Mention component provides built-in compliance with `WAI-ARIA` specifications. The `WAI-ARIA` support is achieved using attributes such as `aria-selected` and `aria-activedescendent`.

## ARIA attributes

The Mention component uses the `Listbox` role where each list item has an option role. The following `ARIA attributes` denote the Mention state.

| **Properties** | **Functionalities** |
| --- | --- |
| `aria-selected` | Indicates the selected option. |
| `aria-activedescendent` | This attribute holds the ID of the active list item to focus its descendant child element. |
| `aria-owns` | This attribute contains the ID of the popup list to indicate the popup as a child element. |

## Keyboard interaction

You can use the following key shortcuts to access the Mention without interruptions.

| **Keyboard shortcuts** | **Actions** |
| --- | --- |

| <kbd>Down arrow</kbd> | Focus the first item in the Mention list. Otherwise, focus the item next to the currently focused item. |
| <kbd>Up arrow</kbd> | Focus the item previous to the currently focused one. |
| <kbd>Esc(Escape)</kbd> | Closes the popup list when it is in an open state. |
| <kbd>Enter</kbd> | Selects the focused item, and when it is in an open state the popup list closes. |
| <kbd>Tab</kbd> | Focuses on the next tabindex element on the page when the popup is closed. Otherwise, inserts the selected popup list item and closes the popup list. |

{% highlight razor %}

{% include_relative code-snippet/accessibility.razor %}

{% endhighlight %}