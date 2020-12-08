<template>
  <div class="container">
    <SearchBar @input-change="onInputChange" />
    <VideoList :videos="videos" />
  </div>
</template>

<script>
import axios from 'axios'
import SearchBar from './components/SearchBar.vue'
import VideoList from './components/VideoList.vue'

// .env.local 파일에 작성한 변수명이 접두사가
// VUE_APP_ 으로 시작한다면 자동으로 설정된다.
// process.env.변수명 으로 아래처럼 작성해 주면된다.
const API_KEY = process.env.VUE_APP_YOUTUBE_API_KEY
const API_URL = 'https://www.googleapis.com/youtube/v3/search'

export default {
  name: 'App',
  components: {
    SearchBar,
    VideoList,
  },
  data() {
    return {
      inputValue: '',
      videos: [],
    }
  },
  methods: {
    onInputChange(inputText) {
      this.inputValue = inputText
      axios.get(API_URL, {
        params: {
          key: API_KEY,
          part: 'snippet',
          type: 'video',
          q: this.inputValue,
        }
      })
        .then(res => this.videos = res.data.items)
        .catch(err => console.error(err))
    }
  }
}
</script>
<style>

</style>
