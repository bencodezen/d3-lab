<script>
import AddSvgExercise from "../components/AddSvgExercise"
import BuildingVisualization from "../components/BuildingVisualization"
import StarbreakCoffee from "../components/StarbreakCoffee"

export default {
  components: {
    AddSvgExercise,
    BuildingVisualization,
    StarbreakCoffee
  }
}
</script>

<template>
  <main class="wrapper">
    <h1>Section 2: Getting Started with D3</h1>
    <h2>Practicing Basic D3 Functions</h2>
    <AddSvgExercise />
    <h2>Generate Rectangles Based on JSON</h2>
    <BuildingVisualization />
    <h2>Starbreak Coffee</h2>
    <StarbreakCoffee />
  </main>
</template>

<style>
.wrapper {
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>
