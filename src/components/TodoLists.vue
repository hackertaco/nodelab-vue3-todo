<template>
<div class="lists-block">
    <draggable :list="todoItems" draggable=".drag-item">
        <div v-for="(todoItem, index) in this.todoItems" :key="index" class="drag-item">
            <i class="fas fa-check checkBtn" @click="toggleComplete({ todoItem, index })" :class="{ checkBtnCompleted: todoItem.completed }"></i>
            <span @click="toggleComplete({ todoItem, index })" :class="{ textCompleted: todoItem.completed }">{{ todoItem.item }}</span>
            <span @click="removeTodo({ todoItem, index })" class="removeBtn"><i class="fas fa-trash"></i></span>
        </div>
    </draggable>
</div>
</template>

<script>
import {
    computed
} from "vue";
import {
    mapMutations,
    useStore
} from "vuex";
import {
    VueDraggableNext
} from "vue-draggable-next";

export default {
    name: "list",

    components: {
        draggable: VueDraggableNext,
    },
    methods: {
        ...mapMutations({
            removeTodo: "removeOneItem",
            toggleComplete: "toggleOneItem",
        }),
    },

    setup() {
        const store = useStore();

        const todoItems = computed(() => {
            return store.getters.getTodoItems;
        });
        return {
            todoItems,
        };
    },
};
</script>

<style>
.lists-block {
    flex-wrap: wrap;
    width: 100%;
    height: 70%;
    display: flex;
    position: absolute;
}

li {
    cursor: pointer;
}

.checkBtn {
    line-height: 45px;
    color: #f8c471;
    margin-right: 10px;
}

.checkBtn:hover {
    cursor: pointer;
    color: #f8f9f9;
}

.checkBtnCompleted {
    color: #b3adad;
}

.textCompleted {
    text-decoration: line-through;
    color: #b3adad;
}

.removeBtn {
    margin-left: 10px;
    color: #f8c471;
}

.removeBtn:hover {
    color: #f8f9f9;
    cursor: pointer;
}
</style>
