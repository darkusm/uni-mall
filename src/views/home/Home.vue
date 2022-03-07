<template>
  <div id="home">
    <nav-bar class="home-nav">
      <div slot="center">购物车</div>
    </nav-bar>
    <home-swiper :banners="banner"></home-swiper>
    <recommend-view :recommends="recommend"></recommend-view>
    <feature-view></feature-view>
    <ul>
      <li>1</li>
      <li>2</li>
      <li>3</li>
      <li>4</li>
      <li>4</li>
      <li>4</li>

      <li>4</li>
      <li>4</li>
      <li>4</li>
      <li>4</li>
      <li>4</li>
      <li>4</li>
      <li>4</li>

      <li>4</li>
    </ul>
  </div>
</template>

<script>
import NavBar from "components/common/navbar/NavBar";
import { getHomeData } from "network/home";
import HomeSwiper from "./childComps/HomeSwiper.vue";
import RecommendView from "./childComps/RecommendView";
// import FeatureView from "./childComps/FeatureView";
import FeatureView from "./childComps/FeatureView.vue";
// import RecommendView from "./childComps/RecommendView.vue";
export default {
  name: "Home",
  components: {
    NavBar,
    HomeSwiper,
    RecommendView,
    RecommendView,
    FeatureView,
    FeatureView,
  },
  data() {
    return {
      // result: null,
      banner: [],
      recommend: [],
    };
  },
  created() {
    let that = this;
    getHomeData().then((res) => {
      // console.log(res);
      // that.result = res;
      // console.log(this.result);
      this.banner = res.data.banner.list;
      this.recommend = res.data.recommend.list;
    });
  },
};
</script>

<style lang="less" scoped>
.home-nav {
  background-color: pink;
  color: white;
  position: fixed;
  top: 0;
  right: 0;
  left: 0;
  z-index: 9;
}
</style>
