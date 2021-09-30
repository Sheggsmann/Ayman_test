<template>
    <button class="btn" :style="{backgroundColor: color}">{{ text }}</button>
</template>

<script>
export default {
    name: 'Button',
    props: {
        text: String,
        color: String,
    }
}
</script>

<style scoped>
.btn {
    padding: 5px 8px;
    font-size: 17px;
    border: none;
    color: royalblue;
    font-weight: bold;
}
</style>