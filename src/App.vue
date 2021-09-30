<template>
  <div class="container">
    <Header title="Xplorer" @display-files="displayFiles" />
    <Files :files="currentFiles" />
  </div>
</template>

<script>
import Header from './components/Header';
import Files from './components/Files';

export default {
  name: 'App',
  components: {
    Header,
    Files,
  },
  data() {
    return {
      selectedFolder: '',
      currentFiles: [],
    }
  },
  methods: {
    displayFiles(folderElement) {
      const files = folderElement.files;
      let tempFiles = [];
      for (let i=0; i<files.length; i++) {
        let fileType = this.checkFileType(files[i].name);
        tempFiles.push({
          key: i,
          fileName: files[i].name,
          fileType,
        })
      }
      this.currentFiles = tempFiles;
    },
    checkFileType(file) {
      let extension = file.split(".").pop();
      let type = "";
      const mediaFiles = ["png", "jpg", "jpeg"];
      const movieFiles = ["mp4", "mov"];
      const musicFiles = ["mp3", "ogg", "wav"];
      const codeFiles = ["js", "py", "cpp", "html", "css", "vue", "jsx", "ts", "tsx"];
      if (mediaFiles.includes(extension)) {
        type = "las la-file-image";
      } else if (movieFiles.includes(extension)) {
        type = "las la-file-video";
      } else if (musicFiles.includes(extension)) {
        type = "las la-file-audio";
      } else if (codeFiles.includes(extension)) {
        type = "las la-file-code";
      } else if (extension === "pdf") {
        type = "las la-file-pdf";
      } else {
        type = "las la-file-alt";
      }
      return type;
    },
  },
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400&display=swap');
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
body {
  font-family: 'Poppins', sans-serif;
}
.container {
  max-width: 500px;
  margin: 30px auto;
  overflow: auto;
  min-height: 90vh;
  border: 1px solid royalblue;
}
.btn {
  display: inline-block;
  background: #000;
  color: #fff;
  border: none;
  padding: 10px 20px;
  margin: 5px;
  border-radius: 5px;
  cursor: pointer;
  text-decoration: none;
  font-size: 15px;
  font-family: inherit;
}
.btn:focus {
  outline: none;
}
.btn:active {
  transform: scale(0.98);
}
.btn-block {
  display: block;
  width: 100%;
}
</style>
