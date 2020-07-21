
<script src="https://d3js.org/d3.v5.min.js"></script>

## Hello, World!

<svg id="viz_area" height=200 width=450></svg>

{% include svg.html %}

<script src="tree.js"></script>

<script>
// Select the svg area
var svg = d3.select("#viz_area")

// Create a scale: transform value in pixel
var x = d3.scaleLinear()
    .domain([0, 100])         // This is the min and the max of the data: 0 to 100 if percentages
    .range([0, 400]);       // This is the corresponding value I want in Pixel
// Try console.log( x(25) ) to see what this x function does.

// Add 3 dots for 0, 50 and 100%
svg.append("circle")
  .attr("cx", x(10)).attr("cy", 100).attr("r", 40).style("fill", "blue");
svg.append("circle")
  .attr("cx", x(50)).attr("cy", 100).attr("r", 40).style("fill", "red");
svg.append("circle")
  .attr("cx", x(100)).attr("cy", 100).attr("r", 40).style("fill", "green");
</script>
