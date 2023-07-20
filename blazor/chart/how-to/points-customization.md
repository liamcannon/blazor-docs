---
layout: post
title: Points Customization in Blazor Charts Component | Syncfusion
description: Checkout and learn here all about Points Customization  in Syncfusion Blazor Charts component and more.
platform: Blazor
control: Chart
documentation: ug
---
<!-- markdownlint-disable MD036 -->
# Points Customization in Blazor

You can customize the series points with different color by using the ``PointColorMapping`` property.

To customize the series points color, folloe the given steps.

**Step 1:**

Define the color in each series and map the value to the series color using ``PointColorMapping`` property in series.

```cshtml

@using Syncfusion.Blazor.Charts                 

<SfChart>
    <ChartEvents TooltipRender="TooltipEvent"></ChartEvents>
    <ChartPrimaryXAxis ValueType="Syncfusion.Blazor.Charts.ValueType.DateTime"></ChartPrimaryXAxis>
    <ChartSeriesCollection>
        <ChartSeries DataSource="@Sales" XName="XValue" PointColorMapping="Color" YName="YValue" Name="Sales" Type="ChartSeriesType.Column">
        </ChartSeries>
    </ChartSeriesCollection>
    <ChartTooltipSettings Enable="true" ></ChartTooltipSettings>
</SfChart>

@code {
    public class ChartData
    {
        public DateTime XValue { get; set; }
        public double YValue { get; set; }
        public string Color { get; set; }
    }

    public List<ChartData> Sales = new List<ChartData>
    {
        new ChartData { XValue = new DateTime(2005, 01, 01), YValue = 21, Color="red" },
        new ChartData { XValue = new DateTime(2006, 01, 01), YValue = 24, Color="blue" },
        new ChartData { XValue = new DateTime(2007, 01, 01), YValue = 36, Color="green" },
        new ChartData { XValue = new DateTime(2008, 01, 01), YValue = 38, Color="pink" },
        new ChartData { XValue = new DateTime(2009, 01, 01), YValue = 20, Color="yellow" },
        new ChartData { XValue = new DateTime(2010, 01, 01), YValue = 30, Color="black" },
        new ChartData { XValue = new DateTime(2011, 01, 01), YValue = 25, Color= "grey" },
        new ChartData { XValue = new DateTime(2012, 01, 01), YValue = 40, Color="blue" },
    };    
}
```
![Blazor Chart With Points Customization](../images/how-to/blazor-chart-points-customization.png)

N> Refer to our [Blazor Charts](https://www.syncfusion.com/blazor-components/blazor-charts) feature tour page for its groundbreaking feature representations and also explore our [Blazor Chart Example](https://blazor.syncfusion.com/demos/chart/line?theme=bootstrap4) to know various chart types and how to represent time-dependent data, showing trends at equal intervals.