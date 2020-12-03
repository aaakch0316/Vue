<template>
    <div>
        <h1>Hanpy</h1>
        <h2>{{ message }}</h2>
    </div>
</template>

<script>
export default {
    name: 'MyComponent',  // 이부분이 디버깅 용이다.
    data: function () {
        return {
            message: 'hi',
            posts: [
                { id: 1, title: 'hi', content: 'hello' }
            ]
        }
    }
}
</script>

<style>

</style>