<template>
<form action="" @submit.prevent="addTodo">
    <fieldset role="group">
    <input 
        v-model = "newTodo"
        type = "text"
        placeholder="Tâche à effectuer">
    <button :disabled="newTodo.length == 0">Ajouter Une Tâche</button>
    </fieldset>
</form>

<div v-if="todos.length == 0">vous n'avez pas de tâche à faire</div>
<div v-else>
    <ul>
        <li v-for="todo in todos"
        :key="todo.date"
        >
        <label>
            <input type="checkbox" v-model="todo.completed">
            {{ todo.title }}
        </label>
        </li>
    </ul>
</div>
</template>


<script setup>
import { ref } from 'vue'

const newTodo = ref('')
const todos = ref([])

const addTodo = () => {
    todos.value.push({
        title:newTodo.value,
        completed : true,
        date : Date.now()
    })
    newTodo.value = ''
}

</script>


