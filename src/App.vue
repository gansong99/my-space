<template>
  <div id="app">
    <h3>图片组件</h3>
    <Avatar
      url="https://img1.sycdn.imooc.com/5fa358fc0880006103920196.jpg"
      :widthsize="150"
      :heightsize="150"
    />
    <div>
      <Icon type="cherry" />
      <Icon type="pineapple" />
      <Icon type="blueberry" />
      <Icon type="strawberry" />
      <Icon type="hamimelon" />
      <Icon type="peach" />
      <Icon type="avocado" />
      <Icon type="persimmon" />
      <Icon type="pitaya" />
      <Icon type="mangosteen" />
      <Icon type="litchi" />
      <Icon type="orange" />
      <Icon type="kiwifruit" />
      <Icon type="banana" />
      <Icon type="apple" />
      <Icon type="lemon" />
      <Icon type="grape" />
      <Icon type="pear" />
      <Icon type="watermelon" />
    </div>
    <Pager
      :total="pagerNumber"
      :current="presend"
      @pageChange="handlePageChange($event)"
    />
  </div>
</template>

<script>
import Avatar from "./components/Avatar/index"
import Icon from "./components/Icon/index"
import Pager from "./components/Pager/index"

export default {
  components: {
    Avatar,
    Icon,
    Pager
  },
  data () {
    return {
      pagerNumber: 302,
      presend: 20
    }
  },
  methods: {
    handlePageChange (newPage) {
      this.presend = newPage;
      console.log("加载当前页数据");
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
