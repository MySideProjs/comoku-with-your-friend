<template>
  <div class="flex flex-col justify-center items-center cursor-pointer">
    <h1>Gomoku with Your Friend!</h1>
    <div id="container" />
  </div>
</template>

<script setup lang="ts">
import textureStone from './texture-stone.jpg'
import textureWood from './texture-wood.jpg'
import Konva from 'konva'
import { onMounted } from 'vue'

const stageHeight = (window.innerHeight * 2) / 3
const stageWidth = (window.innerWidth * 2) / 3
const draw = () => {
  const stage = new Konva.Stage({
    container: 'container',
    width: stageWidth,
    height: stageHeight
  })

  const bgLayer = new Konva.Layer()
  stage.add(bgLayer)

  const imgSource = new Image()
  imgSource.src = textureWood

  const boardImg = new Konva.Image({
    x: 0,
    y: 0,
    width: stageWidth,
    height: stageHeight,
    cornerRadius: 20,
    image: imgSource
  })

  bgLayer.add(boardImg)

  bgLayer.draw()
}

onMounted(draw)
</script>

<style scoped></style>
