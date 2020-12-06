<template>
  <div class="child">
      <h2>자식 컴포넌트</h2>
      {{ propFromParent }}
      <button @click="hungrySignal">부모님!!들리시죠!</button>
  </div>
</template>

<script>
export default {
    name: 'Child',
    // props는 반드시 object를 쓴다. 그래야 검증이 가능하다.
    props: {
        propFromParent: String,
    },
    methods: {
        hungrySignal() {
            this.$emit('hungry') // hungry라는 이벤트를 방출하는 거다.
        }
    }
}
</script>

<style>
    .child {
        border: 3px solid blue;
        margin: 3px;
        padding: 3px;
    }
</style>