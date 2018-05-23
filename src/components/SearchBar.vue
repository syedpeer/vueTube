<template>
    <div class="input-group search">
        <input class="form-control input" placeholder="Search for videos" type="text" @input="onSearch">
    </div>
</template>





<script>
export default {
    name: 'SearchBar',
    methods: {
        onSearch(event) {
            this.$emit('newSearch', event.target.value);
        }
    }
};
</script>

<style scoped>
    .search {
        margin: 2rem 0;
        text-align: center;
    }

    .input {
        width: 75%;
    }
</style>
