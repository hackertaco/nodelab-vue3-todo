<template>
<div class="todo-background">
    <h2>TODOLIST</h2>
    <TodoInput />
</div>
</template>

<script>
import TodoInput from "./TodoInput.vue";

export default {
    name: "TodoTemplate",
    components: {
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
    margin: 100px auto;
    display: flex;
    justify-content: center;
    border-radius: 7%;
    border: 0.3px dotted lightslategrey;
}
</style>
