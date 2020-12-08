<template>
  <ul class="list-group">
    <VideoListItem :video="video" v-for="video in videos" :key="video.etag" />
  </ul>
</template>

<script>
import VideoListItem from './VideoListItem.vue'

export default {
    name: 'VideoList',
    components: {
        VideoListItem
    },
    props: {
        videos: Array,
    }
}
</script>

<style>

</style>