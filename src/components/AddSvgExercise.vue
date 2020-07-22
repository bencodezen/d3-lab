<script>
import * as d3 from "d3"

export default {
  mounted() {
    d3.select("#add-svg-sandbox")
      .append("circle")
      .attr("cx", 100)
      .attr("cy", 100)
      .attr("r", 100)
      .attr("fill", "blue")

    d3.select("#add-svg-sandbox")
      .append("ellipse")
      .attr("cx", 325)
      .attr("cy", 300)
      .attr("rx", 150)
      .attr("ry", 250)
      .attr("fill", "green")

    d3.select("#add-svg-sandbox")
      .append("rect")
      .attr("stroke", "red")
      .attr("stroke-width", 10)
      .attr("x", 10)
      .attr("y", 10)
      .attr("width", 472)
      .attr("height", 372)
      .attr("fill", "transparent")
  }
}
</script>

<template>
  <svg id="add-svg-sandbox" width="500" height="400"></svg>
</template>

<style></style>
