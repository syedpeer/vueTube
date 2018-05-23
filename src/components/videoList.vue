<template>
    <ul class="list-group">
      <videoListItem 
        v-for="video in videos" 
        :key="video.etag"
        :video="video"
        >
        </videoListItem>
    </ul>
</template>

<script>
import videoListItem from './VideoListItem';
export default {
  name: 'VideoList',
  components: {
      videoListItem
  },
  props: {
      videos: Array
  }
};
</script>

