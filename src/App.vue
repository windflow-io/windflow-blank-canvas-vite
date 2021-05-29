<template>
    <h1 class="text-white text-2xl">Welcome </h1>
    <windflow-magic-toolbar/>
</template>

<script lang="ts">

    import {WindflowMagicToolbar} from '@windflow/windflow-magic-toolbar'

    export default {
        name: 'App',
        components: {WindflowMagicToolbar},
        mounted() {
            document.body.classList.add('bg-gray-900');
        }
    }

</script>


