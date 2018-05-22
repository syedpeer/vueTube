<template>
    <ul>
      <videoListItem v-for="video in videos"></videoListItem>
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

