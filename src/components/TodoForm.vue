<script setup>
import { ref, watch } from "vue";

let todoToAdd = ref("");
let onAdd = () => {
    let todos = JSON.parse(localStorage.getItem("Todos")) || [];
    todos.push(todoToAdd.value);
    localStorage.setItem("Todos", JSON.stringify(todos));
    todoToAdd.value = "";
};

</script>

<template>
    <div>
        <input
            type="text"
            @change="
                (e) => {
                    todoToAdd += e.target.value;
                }
            "
            class="todo-input"
        />
        <button @click="onAdd">Add</button>
    </div>
</template>

<style scoped>
div {
    display: flex;
}
.todo-input {
    /* Add your custom styles for the input field */
    font-size: 16px;
    border: 1px solid #ccc;
    padding: 8px;
    border-radius: 4px;
    outline: none; /* Remove default focus outline */
    width: 80%;
}

button {
    /* Add your custom styles for the button */
    background-color: #007bff;
    color: #fff;
    border: none;
    padding: 8px 16px;
    border-radius: 4px;
    cursor: pointer;
    width: 20%;
    text-align: center;
    margin-left: 3px;
}

button:hover {
    background-color: #0056b3;
}
</style>
