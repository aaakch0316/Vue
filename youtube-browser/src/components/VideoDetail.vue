<template>
  <div v-if="video" class="col-lg-8">
    <div class="embed-responsive embed-responsive-16by9">
        <iframe 
            class="embed-responsive-item"
            :src="videoUrl" 
            allowfullscreen
        ></iframe>
    </div>
    <div class="details">
        <h4>{{ video.snippet.title }}</h4>
        <p>{{ video.snippet.description }}</p>
        <!-- {{}} 와 v-text는 같다고 배웠다. 그러나 특정 문자를 안깨지게 하려면 v-html을 사용하자. -->
        <!-- <h4 v-html="video.snippet.title"></h4>
        <p v-html="video.snippet.description"></p> -->
        <!-- v-html은 보안에 취약하다. 왜냐하면 글을 text가 아닌 html로 인식하기 때문이다. 쿠키 접근도 가능하게 된다..-->
        <!-- 결론적으로는 데이터를 받아오는 순간에 변환 안됐으면 약간의 작업을 하면 된다. -->
        <!-- App.vue의 axios 부분에서 받을 때 수정을 하자. -->
    </div>
  </div>
</template>

<script>
export default {
    name: 'VideoDetail',
    props: {
        video: Object,
    },
    computed: {
        videoUrl() {
            // console.log('1')
            return `https://youtube.com/embed/${this.video.id.videoId}`
        }
    }
}
</script>

<style scoped>
    div.details {
        margin-top: 10px;
        padding: 10px;
        border: 1px solid #ddd;
        border-radius: 4px;
    }

</style>