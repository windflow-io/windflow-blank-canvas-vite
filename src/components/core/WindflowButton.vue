<template>
    <div class="relative flex flex-col items-center justify-center py-2 w-10 rounded" :class="selected || 'hover:bg-gray-200'">
        <button class="flex flex-col" v-if="action"><slot/></button>
        <div class="flex flex-col" v-else><slot/></div>
    </div>
</template>

<script>
export default {
    name: "WindflowButton",
    props: [
        'tooltip',
        'action',
        'selected'
    ]
}
</script>
