<template>
    <div class="absolute bg-gray-100 rounded-md top-0 left-0 top-0 ml-10 mt-10 bg-white shadow-md flex flex-row items-center justify-center text-gray-600 text-lg py-3">
        <div class="pl-3 pr-2.5 py-1 border-r border-gray-300 flex cursor-move"><grip-vertical-icon/></div>
        <button class="py-1 px-2.5 border-r border-gray-300 flex flex-col"><plus-icon/></button>
        <button class="py-1 px-2.5 border-r border-gray-300 flex"><edit-icon/></button>
        <button class="py-1 px-2.5 border-r border-gray-300 flex"><code-icon/></button>
        <button class="py-1 px-2.5 border-r border-gray-300 flex"><palette-icon/></button>
        <button class="py-1 px-2.5 border-r border-gray-300 flex"><trash-icon/></button>
        <button class="py-1 px-2.5 border-r border-gray-300 flex"><save-icon/></button>
        <button class="py-1 px-2.5 border-r border-gray-300 flex"><upload-icon/></button>
        <button class="py-1 px-2.5 flex border-r border-gray-300"><cog-icon/></button>
        <button class="py-1 px-2.5 pr-3 flex"><times-icon/></button>
    </div>
</template>

<script setup>

import GripVerticalIcon from "/src/components/icons/GripVerticalIcon.vue";
import PlusIcon from "/src/components/icons/PlusIcon.vue"
import EditIcon from "/src/components/icons/EditIcon.vue"
import CodeIcon from "/src/components/icons/CodeIcon.vue"
import PaletteIcon from "/src/components/icons/PaletteIcon.vue"
import TrashIcon from "/src/components/icons/TrashIcon.vue"
import TimesIcon from "/src/components/icons/TimesIcon.vue"
import UploadIcon from "/src/components/icons/UploadIcon.vue"
import SaveIcon from "/src/components/icons/SaveIcon.vue"
import CogIcon from "/src/components/icons/CogIcon.vue"



</script>
