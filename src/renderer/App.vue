<template>
  <div id="app">
    <custom-header/>
    <div class="main-body">
      <div class="sidebar-left"></div>
      <router-view class="router-view-body"></router-view>
    </div>
  </div>
</template>

<script>
  import CustomHeader from './components/toolkit/CustomHeader/CustomHeader';
  export default {
    name: 'patchouli-electron',
    components: { CustomHeader },
  };
</script>

<style>
.main-body {
  display: flex;
  flex-direction: row;
}

.sidebar-left {
  width: 60px;
  background-color: #e5e5e5;
  height: 100%;
  transition: width 0.28s;
  position: fixed;
}

.router-view-body {
  width: calc(100% - 60px);
  position: fixed;
  margin-left: 60px;
}
</style>
