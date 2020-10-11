<template>
<input type="text" v-model="newTodoItem" @keyup.enter="addTodo" class="todo-input" />
</template>

<script>
export default {
    data() {
        return {
            newTodoItem: "",
        };
    },
    name: "TodoInput",

    methods: {
        addTodo() {
            if (this.newTodoItem !== "") {
                let obj = {
                    completed: false,
                    item: this.newTodoItem
                };
                localStorage.setItem(this.newTodoItem, JSON.stringify(obj));
                this.clearInput();
            }
        },
        clearInput() {
            this.newTodoItem = "";
        },
    },
};
</script>

<style>
.todo-input {
    border: 1px dotted royalblue;
    width: 80%;
    height: 5%;
    border-radius: 10px;
}
</style>
