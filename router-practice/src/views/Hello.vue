<template>
  <div>
      <h1>Hello, {{ name }}</h1>
  </div>
</template>

<script>
export default {
    name: 'Hello',
    data: function() {
        return {
            name : this.$route.params.name,
        }
    }
}
</script>

<style>

</style>