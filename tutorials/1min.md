##What is TauCharts?
TauCharts is a javascript charting library. It is based on an awesome [D3 framework](http://d3js.org/) and [Grammar of Graphics](http://www.amazon.com/The-Grammar-Graphics-Statistics-Computing/dp/0387245448) concepts.

We built TauCharts based on three rules:

1. Graphical design is imporant, so we design everything with passion.
2. Simple charts are easy to create, complex charts are not easy, but possible.
3. Flexibility is important. [Plugins framework](../plugins/README.md) should be powerful.

##How to create a simple line chart?

You have to include d3.js, underscore and taucharts libraries:

```html
<script src="//cdn.jsdelivr.net/d3js/latest/d3.min.js" charset="utf-8"></script>
<script src="//cdn.jsdelivr.net/underscorejs/latest/underscore-min.js" type="text/javascript"></script>
<script src="//cdn.jsdelivr.net/taucharts/latest/tauCharts.min.js" type="text/javascript"></script>
```

Include CSS file:

```html
<link rel="stylesheet" type="text/css" href="//cdn.jsdelivr.net/taucharts/latest/tauCharts.min.css">
```

Then [prepare data](../datasource/README.md) you want to use for the chart. TauCharts accepts data like an array of same-typed objects (it looks like CSV):


```javascript
var datasource = [{
  type:'us', count:20, date:'12-2013'
},{
  type:'us', count:10, date:'01-2014'
},{
  type:'bug', count:15, date:'02-2014'
},{
  type:'bug', count:23, date:'05-2014'
}];
```

Chart definition is extremely simple and speak for itself:

```javascript
var chart = new tauCharts.Chart({
    data: datasource,
    type: 'line',
    x: 'date',
    y: 'count',
    color: 'type' // there will be two lines with different colors on the chart
});
```

Then you just need to render the chart into some HTML element:

```html
<div id='line'>
```

Like that:

```javascript
chart.renderTo('#line');
```

[example jsFiddle](http://jsfiddle.net/taucharts/u86cseky/)

Now find 5 minutes and [read an extended tutorial](5min.md).

