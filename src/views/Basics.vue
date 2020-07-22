<script>
import AddSvgExercise from "../components/AddSvgExercise"
import BuildingVisualization from "../components/BuildingVisualization"

export default {
  components: {
    AddSvgExercise,
    BuildingVisualization
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
  </main>
</template>

<style>
.wrapper {
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>
