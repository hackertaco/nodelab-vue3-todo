<template>
<div class="todo-background">
    <todo-header></todo-header>
    <todo-input></todo-input>
    <todo-lists></todo-lists>
</div>
</template>

<script>
import TodoHeader from "./TodoHeader.vue";
import TodoLists from "./TodoLists.vue";
import TodoInput from "./TodoInput.vue";
export default {
    name: "TodoTemplate",
    components: {
        TodoHeader,
        TodoLists,
        TodoInput,
    },
};
</script>

<style scoped>
.todo-background {
    width: 20rem;
    height: 30rem;
    padding: 2rem;
    background: white;
    margin: 200px auto;
    display: flex;
    justify-content: center;
    border-radius: 7%;
    border: 0.3px dotted lightslategrey;
    flex-wrap: wrap;
}
</style>
