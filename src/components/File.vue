<template>
    <div class="file-item">
        <i :class="fileType"></i>
        <p>{{ fileName }}</p>
    </div>
</template>

<script>
export default {
    name: 'File',
    props: {
        fileName: String,
        fileType: String,
    }
}
</script>

<style scoped>
.file-item {
    display: flex;
    align-items: center;
    justify-content: space-between;
    background-color: #eee;
    padding: 15px;
    margin-bottom: 15px;
}

.file-item i {
    font-size: 35px;
    margin-right: 10px;
}
</style>