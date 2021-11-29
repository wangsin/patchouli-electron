<template>
  <div>
    <button style="height: 60px;width: 100%;">搜索</button>
    <button style="height: 60px;width: 100%;" @click="jumpToRouter('/')">终端</button>
    <button style="height: 60px;width: 100%;">分类</button>
    <button style="height: 60px;width: 100%;">设置</button>
    <button style="height: 60px;width: 100%;">返回</button>
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
