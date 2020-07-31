<script>
import * as d3 from "d3"
import revenue from "../data/revenues.json"

export default {
  mounted() {
    const margin = {
      left: 80,
      right: 30,
      top: 30,
      bottom: 100
    }

    const canvas = {
      width: 600,
      height: 400
    }

    const chart = {
      width: canvas.width - margin.left - margin.right,
      height: canvas.height - margin.top - margin.bottom
    }

    const svg = d3
      .select("#starbreak-sandbox")
      .append("g")
      .attr("transform", `translate(${margin.left}, ${margin.top})`)

    const months = revenue.map(item => item.month)
    const maxRevenue = d3.max(revenue, item => Number(item.revenue))

    const xScale = d3
      .scaleBand()
      .domain(months)
      .range([0, chart.width])
      .paddingInner(0.3)
      .paddingOuter(0.3)

    const yScale = d3
      .scaleLinear()
      .domain([0, maxRevenue])
      .range([chart.height, 0])

    const bottomAxis = d3.axisBottom(xScale)
    const leftAxis = d3.axisLeft(yScale).tickFormat(data => `$${data}`)

    svg
      .append("g")
      .attr("transform", `translate(0, ${chart.height})`)
      .call(bottomAxis)
    svg.append("g").call(leftAxis)

    svg
      .append("text")
      .attr("y", chart.height + 50)
      .attr("x", chart.width / 2)
      .text("Month")
    svg
      .append("text")
      .attr("y", -60)
      .attr("x", -(chart.height / 2))
      .attr("text-anchor", "middle")
      .attr("transform", "rotate(-90)")
      .text("Revenue")

    svg
      .selectAll("rect")
      .data(revenue)
      .enter()
      .append("rect")
      .attr("x", data => xScale(data.month))
      .attr("y", data => yScale(data.revenue))
      .attr("width", xScale.bandwidth)
      .attr("height", data => {
        return chart.height - yScale(Number(data.revenue))
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
  <svg id="starbreak-sandbox" width="600" height="400"></svg>
</template>

<style></style>
