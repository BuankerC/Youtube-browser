<template>
  <ul class="list-group">
    <VideoListItem
      v-for="video in videos"
      :key="video.etag"
      :video="video"
      @videoSelect="onVideoSelect"
    />
    <!-- VideoListItem에서 videoSelect를 받아옴 -->
  </ul>
</template>

<script>
import VideoListItem from "./VideoListItem";
export default {
  name: "videoList",
  props: {
    videos: Array
  },
  components: {
    VideoListItem
  },
  methods: {
    onVideoSelect(video) {
      this.$emit("videoSelect", video);
    }
    // videoSelect라는 이벤트 발생, video에 담아 App.vue로 넘겨줌
  }
};
</script>

<style>
</style>