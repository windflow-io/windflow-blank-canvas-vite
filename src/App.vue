<template>
    <windflow-layout></windflow-layout>
    <windflow-magic-toolbar></windflow-magic-toolbar>

    <animation-one></animation-one>

</template>

<script lang="ts">

    import {WindflowMagicToolbar} from '@windflow/windflow-magic-toolbar'
    import WindflowLayout from '@/components/WindflowLayout.vue';
    import AnimationOne from '@/components/AnimationOne.vue';

    export default {
        name: 'App',
        components: {WindflowLayout, WindflowMagicToolbar, AnimationOne}
    }

</script>


