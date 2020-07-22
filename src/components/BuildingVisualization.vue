<script>
import * as d3 from "d3"
import buildingData from "../data/buildings.json"

export default {
  mounted() {
    const svg = d3.select("#building-sandbox")

    svg
      .selectAll("rect")
      .data(buildingData)
      .enter()
      .append("rect")
      .attr("x", (data, index) => {
        return index * 75 + 50
      })
      .attr("y", 0)
      .attr("width", 50)
      .attr("height", data => {
        return Number(data.height)
      })
      .attr("fill", () => {
        const hue = Math.floor(Math.random() * 360)
        const saturation = Math.floor(Math.random() * 100)
        const lightness = Math.floor(Math.random() * 100)

        return `hsl(${hue}, ${saturation}%, ${lightness}%`
      })
  }
}
</script>

<template>
  <svg id="building-sandbox" width="500" height="400"></svg>
</template>

<style></style>
