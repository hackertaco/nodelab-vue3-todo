<template>
<div class="header-block">
    <div class="header-todo">TODOLIST</div>
    <div class="header-day">{{ day }}요일</div>
</div>
</template>

<script>
export default {
    name: "TodoHeader",
    setup() {
        const week = ["일", "월", "화", "수", "목", "금", "토"];
        const today = new Date();
        const day = week[today.getDay()];
        return {
            day,
        };
    },
};
</script>

<style>
.header-block {
    width: 100%;
    height: 8%;
    text-align: center;
    margin-bottom: 1rem;
}

.header-todo {
    font-size: 1.7rem;
    font-weight: bold;
}

.header-day {
    text-align: center;
    font-size: 0.3rem;
}
</style>
