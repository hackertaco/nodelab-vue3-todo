<template>
<div class="todo-background">
    <todo-header></todo-header>
</div>
</template>

<script>
import TodoHeader from "./TodoHeader.vue";
export default {
    name: "TodoTemplate",
    components: {
        TodoHeader,
    },
};
</script>

<style scoped>
.todo-background {
    display: flex;
    justify-content: center;
    border-radius: 7%;
    flex-wrap: wrap;
}
</style>
