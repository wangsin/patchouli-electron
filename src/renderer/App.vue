<template>
  <div id="app">
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
@import url('./assets/css/font-awesome-4.7.0/css/font-awesome.min.css');
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
