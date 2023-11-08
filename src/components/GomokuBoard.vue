<template>
  <div id="#container" />
</template>

<script setup lang="ts">
import Konva from 'konva'
const stage = new Konva.Stage({
  container: 'container',
  width: 500,
  height: 500
})

const boardLayer = new Konva.Layer()
stage.add(boardLayer)
const circle = new Konva.Circle({
  x: stage.width() / 2,
  y: stage.height() / 2,
  radius: 70,
  fill: 'red',
  stroke: 'black',
  strokeWidth: 4
})
boardLayer.add(circle)

boardLayer.draw()
</script>

<style scoped></style>
