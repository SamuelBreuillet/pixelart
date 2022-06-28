<template>
    <div
        :style="`background-color: ${color}`"
        @click.prevent="setColor(selectedColor)"
        @mouseover="setColor(selectedColor)"
        @mouseleave="setColor(defaultColor)"
    >
    </div>
</template>

<script>
export default {
    name: 'PixelVue',
    props:['selectedColor', 'defaultColor'],
    data() {
        return {
            color: null,
        }
    },
    created() {
        this.color = this.defaultColor
    },
    methods: {
        setColor(color){
            console.log('color')
            this.color = color
        }
    }
    
}
</script>
