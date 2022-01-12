<template>
  <div>
    <div class="np-app-container">
      <div v-if="hasImagePreview" class="np-img-preview-container">
        <img :src="hasImagePreview" class="np-img-preview" />
        <div @click="closeImagePreview()" class="np-img-preview--close">
          Close
        </div>
      </div>
      <div class="np-app-title">Gallery</div>
      <div class="np-gallery-container">
        <div v-for="(image, i) in imagesList" :key="i" class="np-img-thumbnail">
          <img
            @click="setImagePreview(image)"
            :src="image"
            class="np-img-src-tn"
          />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "GalleryView",
  data() {
    return {
      hasImagePreview: null,
    };
  },
  computed: {
    imagesList() {
      let imageIds = [];
      for (let i = 0; i < 14; i++) {
        imageIds.push(Math.floor(Math.random() * 1000) + 1);
      }
      return imageIds.map((img) => {
        return `https://picsum.photos/id/${img}/300/300`;
      });
    },
  },
  methods: {
    setImagePreview(imageToPreview) {
      this.hasImagePreview = imageToPreview;
    },
    closeImagePreview() {
      this.hasImagePreview = null;
    },
  },
};
</script>

<style>
.np-img-thumbnail {
  display: inline-block;
  padding-right: 8px;
}
.np-gallery-container {
  margin-top: 10px;
  margin-left: 4px;
}
.np-img-src-tn {
  width: 60px;
  height: 60px;
  cursor: pointer;
}
.np-img-preview-container {
  position: absolute;
  left: 0px;
  top: 0px;
  background: rgba(0, 0, 0, 0.5);
  height: 500px;
  width: 250px;
}
.np-img-preview {
  position: absolute;
  left: 18px;
  width: 210px;
  height: 210px;
  top: 90px;
  border: 2px solid #000;
  border-radius: 6px;
}
.np-img-preview--close {
  position: absolute;
  color: #fff;
  background: #0059ff;
  border-radius: 6px;
  height: 15px;
  width: 40px;
  right: 24px;
  top: 94px;
  z-index: 99;
  padding: 4px;
  text-align: center;
  font-size: 12px;
  cursor: pointer;
}
</style>