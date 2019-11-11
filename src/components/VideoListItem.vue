<template>
  <li @click="onVideoSelect" class="list-group-item">
    <img :src="thumbnailURL" class="mr-3" />
    {{video.snippet.title}}
  </li>
</template>

<script>
export default {
  name: "VideoListItem",
  props: {
    video: Object
  },
  computed: {
    thumbnailURL() {
      return this.video.snippet.thumbnails.default.url;
    }
  },
  methods: {
    onVideoSelect() {
      this.$emit("videoSelect", this.video);
      // videoselect를 video에 담아 부모인 VideoList로 넘겨줌
    }
  }
};
</script>

<style>
</style>