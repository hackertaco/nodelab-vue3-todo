<template>
<input type="text" v-model="newTodoItem" @keyup.enter="addTodo" class="todo-input" />
</template>

<script>
import {
    ref
} from "vue";
import {
    useStore
} from "vuex";

export default {
    name: "TodoInput",
    setup() {
        const store = useStore();
        const newTodoItem = ref("");

        const addTodo = () => {
            if (newTodoItem.value !== "") {
                const text = newTodoItem.value.trim();
                store.commit("addOneItem", text);
                clearInput();
            }
        };
        const clearInput = () => {
            newTodoItem.value = "";
        };
        return {
            addTodo,
            newTodoItem,
        };
    },
};
</script>

<style>
.todo-input {
    border: 1px dotted royalblue;
    width: 10%;
    height: 3%;
    border-radius: 10px;

    top: 30%;
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
