<template>
    <div class="container">
        <!-- 
            @ = v-on:
            : = v-bind:
         -->
        <SearchBar @newSearch="newSearch"></SearchBar> 
        <div class="row">
            <VideoDetail
                :video="selectedVideo"
                >
            </VideoDetail>
            <VideoList 
                :videos="videos"
                @videoSelect="onVideoSelect"
                >
            </VideoList>
        </div>
    </div>
</template>

<script>
// Components
import SearchBar from './components/SearchBar';
import VideoList from './components/VideoList';
import VideoDetail from './components/VideoDetail';
//Other
import axios from 'axios';
import config from './config/config';

const API_KEY = config.API_KEY;

export default {
    name: 'App',
    components: {
        SearchBar,
        VideoList,
        VideoDetail
    },
    data() {
        return { 
            videos: [], 
            selectedVideo: null
        };
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
        },
        onVideoSelect(video) {
           this.selectedVideo = video
        }
    }
};
</script> 
