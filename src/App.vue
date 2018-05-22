<template>
    <div>
        <!-- 
            @ = v-on:
            : = v-bind:
         -->
        <SearchBar @newSearch="newSearch"></SearchBar> 
        <VideoList :videos="videos"></VideoList>
    </div>
</template>

<script>
import axios from 'axios';
import SearchBar from './components/SearchBar';
import VideoList from './components/videoList';
import config from './config/config';

const API_KEY = config.API_KEY;

export default {
    name: 'App',
    components: {
        SearchBar,
        VideoList
    },
    data() {
        return { videos: [] };
    },
    methods: {
        newSearch(searchTerm) {
          axios.get('https://www.googleapis.com/youtube/v3/search', {
              params: {
                  key: API_KEY,
                  type: 'video',
                  part: 'snippet',
                  q: searchTerm
              }
          }).then(res => {
              this.videos = res.data.items;
          });
        }
    }
};
</script> 
