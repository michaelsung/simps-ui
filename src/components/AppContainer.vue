<template>
    <div id="app-container">
        <h1>S I M P S</h1>
        <p>
            Pull a random image from /r/SimpsonsFaces. DISCLAIMER: Images and Captions are user generated from Reddit.
        </p>
        <ImageGenerator />
    </div>
</template>

<script>
import ImageGenerator from './ImageGenerator.vue'
export default {
    name: 'AppContainer',
    components: {
        ImageGenerator
    }
}
</script>

<style scoped>
h1 {
    margin-bottom: 0px;
}
</style>
