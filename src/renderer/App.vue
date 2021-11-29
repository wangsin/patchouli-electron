<template>
  <div id="app">
    <link href="https://cdn.bootcdn.net/ajax/libs/font-awesome/5.15.3/css/all.min.css" rel="stylesheet">
    <custom-header/>
    <div class="main-body">
      <custom-sidebar class="sidebar-left"/>
      <router-view class="router-view-body"></router-view>
    </div>
  </div>
</template>

<script>
  import CustomHeader from './components/toolkit/CustomHeader/CustomHeader';
  import CustomSidebar from './components/toolkit/CustomSidebar/CustomSidebar.vue';
  export default {
    name: 'patchouli-electron',
    components: { CustomHeader, CustomSidebar },
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

@font-face{
  font-family: Jet-Mono;
  src: url("./assets/fonts/JetBrainsMono-Regular.woff2");
}
</style>
