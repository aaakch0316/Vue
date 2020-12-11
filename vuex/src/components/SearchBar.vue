<template>
  <div class="search-bar">
      <!-- change는 포커스밖으로 나가거나 엔터치거나 하면 함수 실행 -->
      <!-- input으로 하면 키보드 누를 때 마다 반응한다. -->
      <!-- keypress.enter 하면 엔터 칠 때만 된다. -->
      <input @keypress.enter="onInput"> 
  </div>
</template>

<script>
export default {
    name: 'SearchBar',
    methods: {
        onInput(event) {
            // console.log(event.target.value)
            this.$emit('input-change', event.target.value)
        }
    }
}
</script>

// scoped를 쓰면 해당 컴포넌트에만 영향을 준다.
// 그러나 class 지정을 해줘야 빠르다.
<style scoped>
  div.search-bar {
    /* border: 3px solid black;
    padding: 3px;
    margin: 3px; */
    text-align: center;
    margin: 20px;
  }

  div.search-bar > input {
      width: 75%
  }
</style>