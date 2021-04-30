<template>
    <h1 class="text-2xl">{{ msg }}</h1>
    <p class="mt-4">
        <a href="https://vitejs.dev/guide/features.html" target="_blank">Vite Documentation</a> |
        <a href="https://v3.vuejs.org/" target="_blank">Vue 3 Documentation</a> |
        <a href="https://tailwindcss.com/docs/guides/vue-3-vite" target="_blank">Tailwind Setup Documentation</a>
    </p>
    <button @click="state.count++" class="bg-green-500 my-4 p-1 rounded-md border-2 shadow-sm shadow text-white">count is: {{ state.count }}</button>
    <p>
        Edit <code>components/HelloWorld.vue</code> to test hot module replacement.
    </p>
</template>

<script setup>
    import {defineProps, reactive} from 'vue'

    defineProps({
        msg: String
    })

    const state = reactive({count: 0})
</script>

<style scoped>
    a {
        color: #42b983;
    }
</style>
