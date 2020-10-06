<template>
<todo-template />
</template>

<script>
import TodoTemplate from "./components/TodoTemplate.vue";
export default {
    name: "App",
    components: {
        TodoTemplate,
    },
};
</script>

<style>
html {
    width: 100%;
    height: 100vh;
}

body {
    margin: 0;
}

#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    background-color: lightgrey;
    width: 100%;
    height: 100vh;
    margin: 0;
    overflow: hidden;
}
</style>
