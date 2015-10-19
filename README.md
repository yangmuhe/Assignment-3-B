# Assignment-3-B

In this assignment, you will revisit the World Bank dataset we worked with in class to further familiarize yourself with the visualization pipeline as it is implemented in d3. You will practice parsing datasets with incomplete and potentially invalid data; setting scales; drawing axes; and experimenting with different representation strategies for the same data.

An important d3 usage pattern you will practice with is the `.selectAll() -> .data() -> .enter() -> .append()` pattern. Even if you don't fully understand how it works yet, the important thing to understand is that this pattern takes an array of data points, and "joins" each data point to a DOM element (that is to say, an SVG shape), so that each shape--whether a circle, a rectangle, a line, or some other shape--both "contains" and "represents" a data object.

In class, the shape we've chosen has been the `<circle>` element. This doesn't always have to be the case. In this assignment, you will re-interpret the in-class example as a bar graph, drawn with `<line>` elements. Something like this:

[https://cloud.githubusercontent.com/assets/13698981/10542743/6f744da4-73e8-11e5-9f97-f89ac4d63fd5.jpg]

A few things to pay attention to:

## `parse` function

Per inline instructions, completely eliminate data records where gdp per capita is unavailable. For the other data columns, replace unavailable data points with undefined.

## `draw` function

Use the `.selectAll() -> .data() -> .enter() -> .append()` pattern to append new DOM elements

To achieve the bar graph, the DOM element for each country should be roughly organized like so 

```
<g class="country">
  <line class="primaryCompletion" ... > //red line
  <line class="urbanPopulation" ... > //blue line
</g>
