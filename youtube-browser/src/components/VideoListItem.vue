<template>
  <li class="list-group-item">
      <img :src="video.snippet.thumbnails.default.url" alt="youtube-thumbnail-image">
      {{ video.snippet.title }}
  </li>
</template>

<script>
export default {
    name: 'VideoListItem',
    props: {
        video: Object,
    },
}
</script>

<style>

</style>