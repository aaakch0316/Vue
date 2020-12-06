<template>
  <div class="parent">
      <h1>부모 컴포넌트</h1>
      <child @hungry="parentMsg = '왜부르느냐!'" :propFromParent="parentMsg"/>
  </div>
</template>

<script>
import Child from '../components/Child.vue'
export default {
    name: 'Parent',
    data() {
        return {
            parentMsg: '부모에서 내리는 메시지',
        }
    },
    components: {
        // Child, key와 value가 같으면 한번만 쓰는거다.
        Child,
    }
}
</script>

<style>
    .parent {
        border: 3px solid red;
        margin: 3px;
        padding: 3px;
    }
</style>