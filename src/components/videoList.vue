<template>
    <ul>
      <videoListItem 
        v-for="video in videos" :key="video.snippet.id"
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

