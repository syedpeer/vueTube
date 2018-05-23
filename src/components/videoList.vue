<template>
    <ul class="list-unstyled">
      <videoListItem 
        v-for="video in videos" 
        :key="video.etag"
        :video="video"
        @videoSelect="onVideoSelect"
        >
        </videoListItem>
    </ul>
</template>

<script>
import VideoListItem from './VideoListItem';
export default {
  name: 'VideoList',
  components: {
      VideoListItem
  },
  props: {
      videos: Array
  },
  methods: {
      onVideoSelect(video) {
          this.$emit('videoSelect', video);
      }
  }
};
</script>


