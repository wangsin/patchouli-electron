<template>
  <div style="display: flex;flex-direction:column;height: calc(100% - 30px)">
    <div style="height: 60%;">
      <button style="height: 60px;width: 100%;">搜索</button>
      <button style="height: 60px;width: 100%;" @click="jumpToRouter('/')">终端</button>
      <button style="height: 60px;width: 100%;">分类</button>
      <button style="height: 60px;width: 100%;">设置</button>
    </div>
    <div style="display: flex; flex-direction: column-reverse;height: 40%;">
      <button style="height: 60px;width: 100%;">返回</button>
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

</style>
