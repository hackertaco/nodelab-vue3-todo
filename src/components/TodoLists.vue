<template>
<div class="lists-block">
    <ul>
        <li v-for="todoItem in todoItems" :key="todoItem.item">
            <span>{{ todoItem.item }}</span>
        </li>
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
    mounted: function () {
        if (localStorage.length !== 0) {
            for (let i = 0; i < localStorage.length; i++) {
                if (
                    localStorage.key(i) !== "loglevel:webpack-dev-server" &&
                    localStorage.key(i) !== "csCursors"
                ) {
                    console.log(localStorage.key(i));
                    this.todoItems.push(
                        JSON.parse(localStorage.getItem(localStorage.key(i)))
                    );
                }
            }
        }
    },
};
</script>

<style>
.lists-block {
    flex-wrap: wrap;
    width: 100%;
    height: 70%;
    display: flex;
}
</style>
