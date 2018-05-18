<template>
    <div>
        <SearchBar @newSearch="newSearch"></SearchBar>
    </div>
</template>

<script>
import SearchBar from './components/SearchBar';
const API_KEY = 'AIzaSyCdByZNG1KORNJ_SGdl_tCmoc4FMkEot6g';

export default {
    name: 'App',
    components: {
        SearchBar
    },
    methods: {
        newSearch(searchTerm) {
            console.log(API_KEY)
            console.log(searchTerm);
        }
    }
};
</script>
