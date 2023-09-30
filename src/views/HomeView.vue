<script setup lang="ts">
import Heading from '@/components/Heading.vue';
import TodoList from '@/components/TodoList.vue';
import { ref } from 'vue';

const titleText = ref('This is the Homepage');
</script>

<template>
    <main>
        <Heading :title="titleText" />
        <TodoList />
    </main>
</template>
<style scoped>
main {
    display: flex;
    flex-direction: column;
    gap: 1rem;
}
</style>
