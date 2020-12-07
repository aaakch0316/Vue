<template>
  <div class="container">
    <SearchBar @input-change="onInputChange" />
  </div>
</template>

<script>
import axios from 'axios'
import SearchBar from './components/SearchBar.vue'

const API_KEY = '######'
const API_URL = 'https://www.googleapis.com/youtube/v3/search'

export default {
  name: 'App',
  components: {
    SearchBar,
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
