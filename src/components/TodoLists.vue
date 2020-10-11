<template>
<div class="lists-block">
    <ul>
        <li v-for="(todoItem, index) in todoItems" :key="todoItem.item"></li>
    </ul>
</div>
</template>

<script>
export default {
    data: function () {
        return {
            todoItems: [],
        };
    },
    methods: {},
};
</script>

<style>
.lists-block {
    flex: 1;
    width: 100%;
    height: 70%;
    display: flex;
}
</style>
