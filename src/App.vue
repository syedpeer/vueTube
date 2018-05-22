<template>
    <div>
        <SearchBar @newSearch="newSearch"></SearchBar>
        <VideoList></VideoList>
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
    methods: {
        newSearch(searchTerm) {
          axios.get('https://www.googleapis.com/youtube/v3/search', {
              params: {
                  key: API_KEY,
                  type: 'video',
                  part: 'snippet',
                  q: searchTerm
              }
          }).then(res => console.log(res));
        }
    }
};
</script> 
