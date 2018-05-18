<template>
    <div>
        <SearchBar @newSearch="newSearch"></SearchBar>
    </div>
</template>

<script>
import SearchBar from './components/SearchBar';
import config from './config/config';
// const API_KEY = '';

export default {
    name: 'App',
    components: {
        SearchBar
    },
    methods: {
        newSearch(searchTerm) {
            console.log(config.API_KEY)
        }
    }
};
</script> 
