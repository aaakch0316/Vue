<template>
    <div>
        <h1>Hanpy</h1>
        <h2>{{ message }}</h2>
        <ul>
            <button @click="getPosts">데이터 모우기</button>
            <li v-for="post in posts" :key="post.id">
                {{ post.title }}
            </li>
        </ul>
    </div>
</template>

<script>
import axios from 'axios'
export default {
    name: 'MyComponent',  // 이부분이 디버깅 용이다.
    data: function () {
        return {
            message: 'hi',
            posts: []
        }
    },
    methods: {
        getPosts: function() {
            axios.get('https://koreanjson.com/posts')
                .then(res => this.posts = res.data)
        }
    }
}
</script>

<style>

</style>