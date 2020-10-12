<template>
<input type="text" v-model="newTodoItem" @keyup.enter="addTodo" class="todo-input" />
<div class="lists-block">
    <ul>
        <li v-for="(todoItem, index) in todoItems" :key="index">
            <span class="todoItem-content">{{ todoItem.item }}</span>
        </li>
    </ul>
</div>
</template>

<script>
export default {
    data() {
        return {
            newTodoItem: "",
            todoItems: [],
            id: 1,
        };
    },
    name: "TodoInput",
    created: function () {
        if (localStorage.length !== 0) {
            for (let i = 0; i < localStorage.length; i++) {
                if (
                    localStorage.key(i) !== "loglevel:webpack-dev-server" &&
                    localStorage.key(i) !== "csCursors"
                ) {
                    this.todoItems.unshift(
                        JSON.parse(localStorage.getItem(localStorage.key(i)))
                    );
                }
            }
        }
    },
    methods: {
        addTodo() {
            if (this.newTodoItem !== "") {
                let obj = {
                    id: this.id++,
                    completed: "false",
                    item: this.newTodoItem,
                };
                this.todoItems.push(obj);
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

.lists-block {
    flex-wrap: wrap;
    width: 100%;
    height: 70%;
    display: flex;
    justify-content: center;
}

ul {
    list-style: none;

    padding: 0;
}

li {
    padding-bottom: 0.5rem;
}
</style>
