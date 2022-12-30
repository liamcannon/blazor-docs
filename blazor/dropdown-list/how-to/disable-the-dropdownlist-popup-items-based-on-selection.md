---
layout: post
title: Disable the DropDown List Popup items based on selection | Syncfusion
description: Learn how to disable the DropDown List popup items based on the selection in the Syncfusion Blazor DropDown List component.
platform: Blazor
control: DropDown List
documentation: ug
---

# How to disable the DropDown List popup items based on selection

The following example demonstrates how to disable the DropDown List popup items based on the selection in the DropDown List component. This can be achieved by adding the e-disabled class to the selected list.

```cshtml
@using Syncfusion.Blazor
@using Syncfusion.Blazor.DropDowns
<SfDropDownList @ref="DropObj" ID="DDL" TValue="string" ShowClearButton="false" @bind-Value="@DropValue" TItem="Countries" Placeholder="e.g. Australia" DataSource="@Country">
    <DropDownListFieldSettings Text="Name" Value="Code"></DropDownListFieldSettings>
    <DropDownListEvents TValue="string" TItem="Countries" Opened="OnOpen"></DropDownListEvents>
</SfDropDownList>
@code {
    public string DropValue { get; set; } = "BM";
    SfDropDownList<string, Countries> DropObj;
    [Inject]
    protected IJSRuntime JsRuntime { get; set; }
    public class Countries
    {
        public string Name { get; set; }
        public string Code { get; set; }
    }
    List<Countries> Country = new List<Countries>
{
        new Countries() { Name = "Australia", Code = "AU" },
        new Countries() { Name = "Bermuda", Code = "BM" },
        new Countries() { Name = "Canada", Code = "CA" },
        new Countries() { Name = "Cameroon", Code = "CM" },
        new Countries() { Name = "Denmark", Code = "DK" },
        new Countries() { Name = "France", Code = "FR" },
        new Countries() { Name = "Finland", Code = "FI" },
        new Countries() { Name = "Germany", Code = "DE" },
        new Countries() { Name = "Greenland", Code = "GL" },
        new Countries() { Name = "Hong Kong", Code = "HK" },
        new Countries() { Name = "India", Code = "IN" },
        new Countries() { Name = "Italy", Code = "IT" },
        new Countries() { Name = "Japan", Code = "JP" },
        new Countries() { Name = "Mexico", Code = "MX" },
        new Countries() { Name = "Norway", Code = "NO" },
        new Countries() { Name = "Poland", Code = "PL" },
        new Countries() { Name = "Switzerland", Code = "CH" },
        new Countries() { Name = "United Kingdom", Code = "GB" },
        new Countries() { Name = "United States", Code = "US" },
    };
    public async Task OnOpen(PopupEventArgs args)
    {
        await JsRuntime.InvokeVoidAsync("onChange", "DDL", this.DropObj.Value);
    }
}
```

Add the following JavaScript methods inside the script tag of `wwwroot/index.html` (Blazor WebAssembly App) or `Pages/_Layout.cshtml` (Blazor Server App) to disable the DropDown List popup items based on selection.

```cshtml
<script>
window.onChange = (id, ddlValue) => {
    setTimeout(function (e) {
        var ddlObj = document.getElementById(id);
        let lists = ddlObj.blazor__instance.popupObj.element.getElementsByTagName("li");
        for (let list of lists) {
            let value = list.getAttribute("data-value");
            if (ddlValue && ddlValue.includes(value)) {
                list.style.pointerEvents = "none";
                list.classList.add("e-disabled");
            }
        }
    },50)
}
</script>
```