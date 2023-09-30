<script setup lang="ts">
import Heading from '@/components/Heading.vue';
import TodoList from '@/components/TodoList.vue';
import { ref } from 'vue';

const titleText = ref('This is the About Page');
</script>

<template>
    <Heading :title="titleText" />
    <div class="about">
        <h2>This is an about page</h2>
    </div>
</template>
