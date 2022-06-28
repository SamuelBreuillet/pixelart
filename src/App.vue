<template>
    <div id="app">
        <div id="colors">
            <div
                v-for="color in colors"
                :key="color"
                :style="`background-color: ${color}`"
                @click.prevent="setSelectedColor(color)"
            >
            </div>
        </div>
        
        <div id="pixelArt">
            <Pixel
                v-for="n in 121"
                :key="n"
                :selected-color="selectedColor"
                :default-color="defaultColor"
            ></Pixel>
        </div>
    </div>
</template>

<script>
import Pixel from "@/components/Pixel";

export default {
    name: 'App',
    components: {
        Pixel
    },
    data() {
        return {
            colors: ['#FC0000', '#FFD602', '#238B21', '#1C90FF', '#000'],
            defaultColor: '#1C90FF',
            selectedColor: null
        }
    },
    created() {
        this.selectedColor = this.colors[0]
    },
    methods: {
        setSelectedColor(color) {
            this.selectedColor = color
        }
    },
}
</script>

<style>
#colors {
    display: grid;
    grid-template-columns: repeat(12, 50px);
    grid-auto-rows: minmax(50px, auto);
}

#pixelArt {
    display: grid;
    grid-template-columns: repeat(11, 50px);
    grid-auto-rows: minmax(50px, auto);
    grid-gap: 1px;
    background-color: black;
    width: 561px;
}

#pixelArt div {
    border: solid black 1px;
}
</style>
