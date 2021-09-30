<template>
    <header>
        <h1>{{ title }}</h1>
        <Button text="Select Folder" color="white" @click="trigger" />
        <input type="file" hidden webkitdirectory directory ref="folderInput" @change="handleFolder">
    </header>
</template>

<script>
import Button from './Button';

export default {
    name: "Header",
    props: {
        title: String,
    },
    components: {
        Button,
    },
    data() {
        return {
            folderName: "",
        }
    },
    methods: {
        trigger() {
            this.$refs.folderInput.click();
        },
        handleFolder(evt) {
            this.$emit('display-files', evt.target);
        }
    }
}
</script>

<style scoped>
header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    background-color: royalblue;
    padding: 10px;
    color: #fff;
}
</style>