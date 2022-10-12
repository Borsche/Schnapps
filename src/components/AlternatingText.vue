<template>
    <div class="container">
        <ImageText 
            v-for="(test,i) in tests" 
            v-bind:key="i" 
            :left="(i % 2) == 0"/>
    </div>
</template>

<script>
import ImageText from './ImageText.vue'

export default {
    name: "AlternatingText",
    components: {
        ImageText,
    },
    data() {
        return {
            tests: [
                {
                    imgSrc: '',
                    text: '', 
                },
                {

                },
                "text",
                "text",
                "text",
                "text",
                "text",
            ]
        }
    }
}
</script>

<style scoped>
    .container {
        padding-top: 25px;
    }
</style>