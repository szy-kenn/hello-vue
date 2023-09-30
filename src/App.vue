<script setup lang="ts">
const todos = ['Learn Vue', 'Learn Tailwind', 'Learn Nuxt'];
</script>

<template>
    <nav>
        <RouterLink to="/">Home</RouterLink>
        <RouterLink to="/about">About</RouterLink>
    </nav>
    <div class="view">
        <RouterView />
    </div>
</template>

<style scoped>
nav {
    display: flex;
    gap: 2rem;
    padding: 1rem 2rem;
    background: rgb(51, 50, 50);
}

nav > a {
    color: white;
    text-decoration: none;
    font-weight: bold;
    font-size: 0.825rem;
}

.view {
    display: flex;
    flex-direction: column;
    padding: 1rem 2rem;
}
</style>
