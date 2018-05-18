<template>
    <div>
        <input type="text" v-on:input="onSearch">
    </div>
</template>

<script>
export default {
    name: 'SearchBar',
    methods: {
        onSearch: function(event) {
            console.log(event.target.value);
        }
    }
};
</script>

<style>
</style>
