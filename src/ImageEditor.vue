<template>
  <div>
    <canvas ref="canvas" width="400" height="400"></canvas>
  </div>
</template>

<script>
import { fabric } from 'fabric'

export default {
  name: 'ImageEditor',
  data() {
    return {
      canvas: null,
      image: null
    }
  },
  mounted() {
    this.canvas = new fabric.Canvas(this.$refs.canvas)
    this.canvas.setWidth(400)
    this.canvas.setHeight(400)
  },
  methods: {
    async loadImage(imageUrl) {
      this.image = await fabric.Image.fromURL(imageUrl, (img) => {
        console.log(img)
        img.set({ selectable: true, resizable: true })
        this.canvas.add(img)
        this.canvas.centerObject(img)
        this.canvas.renderAll()
      })
    }
  }
}
</script>
