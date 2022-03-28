<template>
  <div style="display: flex;flex-direction:column;height: calc(100% - 30px)">
    <div style="height: 60%;">
      <button class="nvi-btn fa fa-search fa-1x"></button>
      <button class="nvi-btn fa fa-terminal fa-1x" @click="jumpToRouter('/')"></button>
      <button class="nvi-btn fa fa-book fa-1x"></button>
      <button class="nvi-btn fa fa-cogs fa-1x"></button>
    </div>
    <div style="display: flex; flex-direction: column-reverse;height: 40%;">
      <button style="background-color: transparent;" class="nvi-btn fa fa-circle-o-notch fa-spin fa-fw"></button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'CustomSidebar',
  methods: {
    open(link) {
      this.$electron.shell.openExternal(link);
    },
    jumpToRouter(router) {
      this.$router.push(router);
    },
  },
};
</script>

<style scoped>
.nvi-btn {
  height: 60px;
  width: 100%;
  border: none;
  color: #525252;
  text-decoration: none;
}

.nvi-btn:hover {
  color: #fff;
  background-color: #0074D9;
  border: none;
  outline: none;
}

.nvi-btn:active {
  background-color: #0067c7;
  border: none;
  outline: none;
}

a,button,input {
  outline: none;
  -webkit-tap-highlight-color: rgba(255, 255, 255, 0);
  -webkit-user-modify: read-write-plaintext-only;
}
</style>
