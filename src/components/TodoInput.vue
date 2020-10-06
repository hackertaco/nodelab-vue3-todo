<template>
<input v-on="click" class="todo-input" />
</template>

<script>
export default {
    name: "TodoInput",
};
</script>

<style>
.todo-input {
    top: 25%;
    position: absolute;
}
</style>
