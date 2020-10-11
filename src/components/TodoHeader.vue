<template>
<div class="header-block">
    <div class="header-day">day</div>
    <div class="header-todo">TODOLIST</div>
</div>
</template>

<script>
export default {
    name: "TodoHeader",
};
</script>

<style>
.header-block {
    width: 100%;
    height: 8%;
    text-align: center;
}

.header-todo {
    font-size: 1.7rem;
    font-weight: bold;
}

.header-day {
    text-align: right;
    font-size: 0.3rem;
}
</style>
