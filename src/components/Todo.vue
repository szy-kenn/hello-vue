<script setup lang="ts">
defineProps(['todo']);
</script>
<template>
    <input
        type="checkbox"
        :name="todo.text"
        :id="`todo-${todo.id}`"
        :key="todo.id"
        :checked="todo.done"
        @change="todo.done = !todo.done"
    />
    <label :for="`todo-${todo.id}`" :class="todo.done ? 'completed' : 'todo'">{{
        todo.text
    }}</label>
</template>
<style scoped>
label.completed {
    text-decoration: line-through;
}

label.todo {
    text-decoration: none;
}
</style>
