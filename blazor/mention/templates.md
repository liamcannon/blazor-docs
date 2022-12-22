---
layout: post
title: Templates in Blazor Mention Component | Syncfusion
description: Checkout and learn here all about templates in Syncfusion Blazor Mention component and much more.
platform: Blazor
control: Mention
documentation: ug
---

# Templates in Blazor Mention Component

Mention is a templated blazor component, that allow you to customize various part of the UI using template parameters. It allows you to render custom components or content based on your own logic. The Mention has been provided with several options to customize each suggestion list items.

## Template context

The templates used by the Mention component are of type `RenderFragment`, which is a special type of delegate that represents a block of Razor code that can be rendered as part of a component's user interface. The templates used by the Mention component are passed parameters that can be accessed using an implicit parameter named `context`.

## Item template

The `ItemTemplate` property allows you to specify a custom template for each individual suggestion list item in the Mention component. This template can be used to customize the content and appearance of the list items based on your own requirements.

In the following sample, each list item is split into two columns to display relevant data using `ItemTemplate`.

{% highlight razor %}

{% include_relative code-snippet/item-template.razor %}

{% endhighlight %}

![Blazor Mention with item template](./images/blazor-mention-item-template.png)

## Display template

The `DisplayTemplate` property allows you to specify a template that defines how the mentioned value should be displayed in the Mention component. You can customize the appearance of the mentioned value, such as by adding an avatar or displaying additional information about the mentioned value.

In the following sample, the selected value is displayed as a combined text of both `FirstName` and `City` in the Mention element, which is separated by a hyphen.

{% highlight razor %}

{% include_relative code-snippet/display-template.razor %}

{% endhighlight %}

![Blazor Mention with display template](./images/blazor-mention-display-template.png)

## No records template

The `NoRecordsTemplate` property in Mention allows you to specify a custom template to be displayed when no data or matches are found during a search. This can be useful in certain situations, such as when you want to display a message or other content to the user to indicate that no matches were found.

{% highlight razor %}

{% include_relative code-snippet/no-record-template.razor %}

{% endhighlight %}

![Blazor Mention with no record template](./images/blazor-mention-noRecord-template.png)

## Spinner template

The `SpinnerTemplate` property in Mention allows you to specify a custom template to be displayed when data is being fetched and the suggestion list is in the process of loading. This can be useful in certain situations, such as when you want to display a waiting spinner or other visual indicator to the user to indicate that data is being fetched.

{% highlight razor %}

{% include_relative code-snippet/spinner-template.razor %}

{% endhighlight %}

![Blazor Mention with spinner template](./images/blazor-mention-spinner-template.png)

## See also

* [How to achieve filtering](./filtering)