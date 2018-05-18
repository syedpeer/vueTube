<template>
    <div>
        <SearchBar @newSearch="newSearch"></SearchBar>
    </div>
</template>

<script>
import axios from 'axios';
import SearchBar from './components/SearchBar';
import config from './config/config';

const API_KEY = config.API_KEY;

export default {
    name: 'App',
    components: {
        SearchBar
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
