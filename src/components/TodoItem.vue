<script setup>
import { defineProps } from "vue";

const props = defineProps({
    title: String,
});
</script>

<template>
    <div class="todo-item">
        <input type="text" class="todo-title" readonly :value="title" />
        <div class="buttons">
            <button class="edit-button">Edit</button>
            <button class="done-button">Done</button>
        </div>
    </div>
</template>

<style scoped>
.todo-item {
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin: 10px 0;
}

.todo-title {
    flex: 1;
    padding: 8px;
    border: 1px solid #ccc;
    border-radius: 4px;
    outline: none;
    font-size: 15px;
}

.buttons {
    margin-left: 3px;
    display: flex;
    gap: 3px;
}

button {
    padding: 8px 16px;
    border: none;
    border-radius: 4px;
    cursor: pointer;
}

.edit-button {
    background-color: #007bff;
    color: #fff;
}

.done-button {
    background-color: #28a745;
    color: #fff;
}
</style>
