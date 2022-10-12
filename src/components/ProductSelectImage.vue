<template>
    <div id="image">
    </div>
</template>
<script>
export default {
    name: 'ProductSelectImage',
    props: {
        msg: String,
        img: String
    }
}
</script>

<style scoped>
    #image {
        border-radius: 15px;
        width: 220px;
        height: 350px;
        background-color: white;
    }
</style>