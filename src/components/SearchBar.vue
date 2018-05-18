<template>
    <div>
        <input type="text" @input="onSearch">
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

<style>
</style>
