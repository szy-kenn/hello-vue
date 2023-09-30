<script setup lang="ts">
import { ref } from 'vue';
import Todo from './Todo.vue';

let idCount = ref(0);

const newTask = ref('');

const todos = ref([
    { id: idCount.value++, text: 'Learn Vue', done: false },
    { id: idCount.value++, text: 'Learn Tailwind', done: false },
    { id: idCount.value++, text: 'Learn Nuxt', done: false },
]);

const doneTasks = () => {
    let count = 0;

    for (let todo of todos.value) {
        if (todo.done) {
            count++;
        }
    }

    return count;
};

const addTask = (task: string) => {
    todos.value.push({ id: idCount.value++, text: task, done: false });
    newTask.value = '';
};

const deleteTask = (todo: { id: number; text: string; done: boolean }) => {
    todos.value = todos.value.filter((t) => t.id !== todo.id);
};
</script>

<template>
    <div class="wrapper">
        <h3>Tasks completed: {{ doneTasks() }}</h3>
        <h3>Tasks to do: {{ todos.length - doneTasks() }}</h3>
        <div>
            <input type="text" v-model="newTask" />
            <button @click="addTask(newTask)">Add Task</button>
        </div>
        <ul>
            <li v-for="todo in todos">
                <Todo :todo="todo" />
                <button @click="deleteTask(todo)">Delete</button>
            </li>
        </ul>
    </div>
</template>

<style scoped>
.wrapper {
    display: flex;
    flex-direction: column;
    justify-content: space-around;
    gap: 1rem;
}

li {
    display: flex;
    align-items: center;
    gap: 1rem;
    padding: 0.5rem 0;
}

li > button {
    padding: 0.5rem 1rem;
    border-radius: 0.5rem;
    border: none;
    background: rgb(63, 59, 59);
    color: white;
    cursor: pointer;
}
</style>
