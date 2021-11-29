<template>
  <div class="header">
    <div class="title-group">
      <img src="src/renderer/assets/patchouli-logo-alpha.png" class="header-icon" alt="icon">
      Patchouli Electron Branch Alpha v0.0.1 - 开发版本
    </div>
    <div class="btn-group">
      <button class="btn btn-close" @click="close()"></button>
      <button class="btn btn-max" @click="toMax()"></button>
      <button class="btn btn-min" @click="toMin()"></button>
    </div>
  </div>
</template>

<script>

export default {
  name: 'CustomHeader',
  methods: {
    toMin() {
      this.$electron.ipcRenderer.send('window-min');
    },
    toMax() {
      this.$electron.ipcRenderer.send('window-max');
    },
    close() {
      this.$electron.ipcRenderer.send('window-close');
    },
  },
};
</script>

<style scoped>
.header {
  padding-left: 10px;
  padding-right: 10px;
  color: #ffffff;
  width: 100%;
  height: 30px;
  display: flex;
  align-items: center;
  -webkit-app-region: drag;
  background-color: gray;
  font-family: Jet-Mono, '思源黑体', 'Source Sans Pro', sans-serif;
  font-size: 12px;
}

.header-icon {
  height: 16px;
  width: 16px;
  margin-right: 8px;
}

.title-group {
  width: 90%;
  display: flex;
  align-items: center;
}

.btn-group {
  display: flex;
  align-items: center;
  flex-direction: row-reverse;
  width: 10%;
}

.btn {
  -webkit-app-region: no-drag;
  margin-left: 3px;
  margin-right: 3px;
  padding: 1px;
  text-align: center;
  text-decoration: none;
  border: none;
  color: white;
  display: inline-block;
  height: 12px;
  width: 12px;
  background-color: #e5e5e5;
  -webkit-transition-duration: 0.4s; /* Safari */
  transition-duration: 0.4s;
  border-radius: 100%;
}

.btn:hover {
  background-color: white; /* Green */
  color: #000;
}

.btn-close:hover {
  background-color: orangered; /* Green */
  color: white;
}

.btn-max:hover {
  background-color: yellow; /* Green */
  color: white;
}

.btn-min:hover {
  background-color: lawngreen; /* Green */
  color: white;
}
</style>
