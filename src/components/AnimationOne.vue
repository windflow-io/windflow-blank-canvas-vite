<template>
        <section>
            <div class="border-2 border-gray-500 rounded-lg font-mono bg-black text-white w-2/3 mt-10 ml-10 overflow-hidden">
                <div class="bg-gray-800 p-3 flex ">
                    <div class="rounded-full w-4 h-4 bg-red-500"></div>
                    <div class="rounded-full w-4 h-4 bg-yellow-500 ml-2"></div>
                    <div class="rounded-full w-4 h-4 bg-green-500 ml-2"></div>
                </div>
                <div class="p-3">
                    <div class="text-green-600">
                        <span v-if="mode==='new'"># New Project</span>
                        <span v-if="mode==='existing'"># Existing Project</span>
                    </div>
                    <span class="font-bold text-green-400"> &gt;</span>&nbsp;{{ liveDisplay }}<span :class="{'hidden':cursorVisible}" class="text-green-400">&#9602;</span>

                </div>
            </div>
        </section>
</template>

<script lang="ts">
export default {
    name: "AnimationOne",
    data() {
        return {
            length: 0,
            newText: "git clone https://github.com/windflow-io/windflow-blank-canvas-vite.git",
            existingText: "npm i @windflow/windflow-magic-toolbar",
            mode: "new",
            text: "",
            going: true,
            waiting: false,
            cursorVisible: false
        }
    },
    computed: {
        liveDisplay: function() {
            return this.text.substr(0, this.length);
        }
    },
    mounted() {
        this.text = this.newText;
        setInterval(() => this.cursorVisible = !this.cursorVisible, 500);
        setInterval(() => {
            if (this.length < this.text.length && this.going) {
                if (Math.floor( Math.random() * 2) === 1) this.length +=  1;
                this.cursorVisible = false;
            } else if (this.length == this.text.length && !this.waiting) {
                this.waiting = true;
                this.going = false;
                setTimeout(() => {
                    this.length = 0
                    if (this.mode === 'new') {
                        this.text = this.existingText;
                        this.mode = 'existing'
                    } else {
                        this.text = this.newText;
                        this.mode = 'new'
                    }

                }, 2000);
                setTimeout(() => {this.going = true; this.waiting= false}, 4000);
            }

        }, 40)
    }
}
</script>
