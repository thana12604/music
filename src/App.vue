<template>
<div id="app">
    <work />
</div>
</template>

<script>
import Work from './components/Work.vue'
export default {
    name: 'App',
    components: {
        Work

    }
}
</script>

<style>
#app {
    font-family: 'Athiti', sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
}

body {
    background-image: url('https://sweet-summer.com/wp-content/uploads/2020/04/SweetSummer_background_Majory-700x394.jpg');
    background-attachment: fixed;
    background-position: center;
    background-repeat: no-repeat;
    background-size: cover;
}
</style>
