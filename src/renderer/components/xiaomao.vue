<template>
  <div id="app">
    <div v-for="file in files" class="file">
      <h4>{{ file.name }}</h4>
      <p>{{ file.size }}k</p>
      <p v-if="file.size > 20">This file is larger than 20k</p>
    </div>
    <div>
      <h4>New file</h4>
      <input v-model="newFileName" type="text" placeholder="file name">
      <br>
      <input v-model="newFileSize" type="number" placeholder="file size">
      <br>
      <button v-on:click="createFile">Create</button>
    </div>
  </div>
</template>
<!--template: 这个vue object的内容-->

<script>
export default {
  name: 'app',
  data: function () {
    return {
      newFileName: '醒醒你生不出小猫的',
      newFileSize: 233,
      files: [{name: 'file1.txt', size: 10}, {name: 'file2.txt', size: 20}, {name: 'file3.txt', size: 30}]
    }
  },
  methods: {
    createFile: function () {
      this.files.push({
        name: this.newFileName,
        size: this.newFileSize
      })
    }
  }
}
</script>
<!-- script:  这个vue object的逻辑-->

<style>
body {
  margin: 0;
}

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}

main {
  text-align: center;
  margin-top: 40px;
}

header {
  margin: 0;
  height: 56px;
  padding: 0 16px 0 24px;
  background-color: #35495E;
  color: #ffffff;
}

header span {
  display: block;
  position: relative;
  font-size: 20px;
  line-height: 1;
  letter-spacing: .02em;
  font-weight: 400;
  box-sizing: border-box;
  padding-top: 16px;
}
</style>
<!-- 这个vue object的样式-->
