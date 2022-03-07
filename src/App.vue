<template>
  <div id="app" class="wrapper">
    <router-view class="view" />
    <main-tab-bar class="tab-bar" />
  </div>
</template>

<script>
import MainTabBar from "components/content/mainTabbar/MainTabBar";

export default {
  name: "app",
  components: {
    MainTabBar,
  },
};
</script>

<style>
@import "assets/css/base.css";
.view {
  margin: 40px 0 60px 0;
}
</style>
