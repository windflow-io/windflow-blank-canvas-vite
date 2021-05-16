<template>
    <windflow-layout></windflow-layout>
    <windflow-magic-toolbar></windflow-magic-toolbar>
    
    <animation-one></animation-one>

</template>

<script lang="ts">

    import WindflowMagicToolbar from '@/components/WindflowMagicToolbar.vue'
    import WindflowLayout from '@/components/WindflowLayout.vue';
    import AnimationOne from '@/components/AnimationOne.vue';

    export default {
        name: 'App',
        components: {WindflowLayout, WindflowMagicToolbar, AnimationOne}
    }

</script>


