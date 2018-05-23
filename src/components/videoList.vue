<template>
    <ul class="list-unstyled col-md-4 col-xs-12">
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
  props: ['videos'],
  methods: {
      onVideoSelect(video) {
          this.$emit('videoSelect', video);
      }
  }
};
</script>


