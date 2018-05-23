<template>
    <li class="item media mb-3">
        <img class="mr-3" :src="thumbnailUrl" />
        <div class="media-body">
            {{video.snippet.title}}
        </div>
    </li>
</template>

<script>
export default {
    name: 'VideoListItem',
    props: {
        video: Object
    },
    computed: {
        thumbnailUrl() {
           return this.video.snippet.thumbnails.default.url;
        }
    }
}
</script>

<style scoped>
    .item {
        cursor: pointer;
    }
    .item:hover {
        background-color: #eee;
    }
</style>

