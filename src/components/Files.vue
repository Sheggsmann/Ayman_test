<template>
    <div class="files">
      <div v-for="file in files" :key="file.id">
          <File :fileName="file.fileName" :fileType="file.fileType" />
      </div>      
    </div>    
</template>

<script>
import File from './File';

export default {
    name: 'Files',
    props: {
      files: Array,  
    },
    components: {
        File,
    },
}
</script>

<style scoped>
.files {
    height: 80vh;
    overflow-x: hidden;
    overflow-y: auto;
    padding: 25px;
}
</style>
