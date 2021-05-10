<template>
    <div ref="windflowMagicToolbar" class="absolute bg-gray-100 rounded-md shadow-md flex flex-col items-center justify-center text-gray-600 text-lg py-2" :style="{left:positionX + 'px', top:positionY + 'px'}">
        <div class="flex flex-row">

            <windflow-button class="cursor-move" @mousedown="dragDown($event)">
                <grip-vertical-icon/>
            </windflow-button>

            <div class="w-0 border-r h-5 mt-2 border-gray-500"></div>

            <windflow-button @mouseover="statusbarText = 'Add component'" @mouseout="statusbarText = ''">
                <plus-icon/>
            </windflow-button>

            <windflow-button @mouseover="statusbarText = 'Edit content'" @mouseout="statusbarText = ''">
                <edit-icon/>
            </windflow-button>

            <windflow-button @mouseover="statusbarText = 'Edit code'" @mouseout="statusbarText = ''" selected="bg-blue-200 hover:bg-blue-300">
                <code-icon/>
            </windflow-button>

            <windflow-button @mouseover="statusbarText = 'Remove component'" @mouseout="statusbarText = ''">
                <trash-icon/>
            </windflow-button>

            <windflow-button @mouseover="statusbarText = 'Save all'" @mouseout="statusbarText = ''">
                <save-icon/>
            </windflow-button>

            <windflow-button @mouseover="statusbarText = 'Publish all'" @mouseout="statusbarText = ''">
                <upload-icon/>
            </windflow-button>

            <windflow-button @mouseover="statusbarText = 'Close'" @mouseout="statusbarText = ''">
                <times-icon/>
            </windflow-button>
        </div>
        <div class="flex pl-2 w-full items-start text-xs items-center transform ease-linear duration-200" :class="statusbarText ? 'pt-1 h-4':'h-0'"><span>{{statusbarText}} <!--<edit-icon/>--></span></div>
    </div>
</template>

<script>

import PlusIcon from '/src/components/core/icons/PlusIcon.vue'
import CodeIcon from '/src/components/core/icons/CodeIcon.vue'
import EditIcon from '/src/components/core/icons/EditIcon.vue'
import SaveIcon from '/src/components/core/icons/SaveIcon.vue'
import TrashIcon from '/src/components/core/icons/TrashIcon.vue'
import UploadIcon from '/src/components/core/icons/UploadIcon.vue'
import TimesIcon from '/src/components/core/icons/TimesIcon.vue'
import WindflowButton from '/src/components/core/WindflowButton.vue'
import GripVerticalIcon from "/src/components/core/icons/GripVerticalIcon.vue";


export default {
    name: 'WindflowMagicToolbar',
    components: {
        GripVerticalIcon,
        CodeIcon, PlusIcon, EditIcon, SaveIcon, TrashIcon, UploadIcon, TimesIcon, WindflowButton
    },
    data() {
        return {
            statusbarText: '',
            positionX:'200',
            positionY:'200',
            mouseOffsetX:0,
            mouseOffsetY:0,
        }
    },
    methods: {
        dragDown(e) {
            this.mouseOffsetX = e.clientX - this.$refs.windflowMagicToolbar.getBoundingClientRect().x;
            this.mouseOffsetY = e.clientY - this.$refs.windflowMagicToolbar.getBoundingClientRect().y;
            window.addEventListener('mousemove', this.dragMove)
            window.addEventListener('mouseup',this.dragUp)
        },
        dragMove(e) {
            this.positionX = e.clientX - this.mouseOffsetX;
            this.positionY = e.clientY - this.mouseOffsetY;
        },
        dragUp() {
            window.removeEventListener('mousemove', this.dragMove);
            window.removeEventListener('mouseup', this.dragUp);
        }
    }
}


</script>
