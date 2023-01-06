<template>
  <div>
    <image-editor ref="editor"></image-editor>
    <button
      @click="
        loadImage(
          'https://www.pngmart.com/files/5/Black-Cat-PNG-Free-Download.png'
        )
      "
    >
      Load
    </button>
  </div>
</template>

<script>
import ImageEditor from './ImageEditor.vue'

export default {
  name: 'App',
  components: {
    ImageEditor
  },
  methods: {
    loadImage(imageUrl) {
      console.log(imageUrl)
      this.$refs.editor.loadImage(imageUrl)
    }
  }
}
</script>
