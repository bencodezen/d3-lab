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
      .append("rect")
      .attr("stroke", "red")
      .attr("stroke-width", 8)
      .attr("x", 10)
      .attr("y", 10)
      .attr("width", 484)
      .attr("height", 384)
      .attr("fill", "transparent")
  }
}
</script>

<template>
  <main>
    <h1>Section 2: Getting Started with D3</h1>
    <svg id="add-svg-sandbox" width="500" height="400"></svg>
  </main>
</template>

<style></style>
