<template>
    <div
        :key="updateCounter"
        :style="`background-color: ${color}`"
        @click.prevent="setColor(selectedColor)"
        @mouseover="previewColor(selectedColor)"
        @mouseleave="restoreColor(resetColor)"
    >
    </div>
</template>

<script>
export default {
    name: 'PixelVue',
    props: ['selectedColor', 'defaultColor'],
    data() {
        return {
            color: null,
            resetColor: null,
            updateCounter: 0
        }
    },
    created() {
        this.color = this.defaultColor
        this.resetColor = this.defaultColor
    },
    methods: {
        setColor(color) {
            console.log(color)
            this.color = color
            this.updateCounter++
        },
        previewColor(color) {
            this.resetColor = this.color;
            this.color = color
        },
        restoreColor(color) {
            this.color = color;
        }
    }
    
}
</script>
