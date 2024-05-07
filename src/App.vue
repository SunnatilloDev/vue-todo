<script setup>
import { ref } from "vue";
import TodoForm from "./components/TodoForm.vue";
import TodoItem from "./components/TodoItem.vue";

let todos = ref(JSON.parse(localStorage.getItem("Todos")) || []);
</script>

<template>
    <div class="App">
        <h1>Todo App</h1>
        <TodoForm />
        <div v-for="(todo, index) in todos" :key="index">
            <TodoItem :title="todo" />
        </div>
    </div>
</template>

<style scoped>
.App {
    max-width: 500px;
    margin: 50px auto;
    padding: 20px;
    min-height: 600px;
    text-align: center;
    border-radius: 4px;
    border: 2px solid;
}
</style>
