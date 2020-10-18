<template>
<span class="clearAll" @click="clearTodo">⚡️</span>
<todo-template />
<todo-input />
<todo-lists />
</template>

<script>
import TodoTemplate from "./components/TodoTemplate.vue";
import TodoInput from "./components/TodoInput.vue";
import TodoLists from "./components/TodoLists.vue";
export default {
    name: "App",
    components: {
        TodoTemplate,
        TodoLists,
        TodoInput,
    },
    methods: {
        clearTodo() {
            localStorage.clear();
        },
    },
};
</script>

<style>
.clearAll {
    padding: 5px;
    color: black;
    font-size: 4rem;
}

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
