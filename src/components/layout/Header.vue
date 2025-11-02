<template>
  <header>
    <img class="logo" src="../../assets/image/logo2.jpg" alt="" @click="goHome()" />
    <div class="header-tabs">
      <div class="tab" v-for="value in tabs" @click="goLink(value.link)">{{ value.name }}</div>
    </div>
    <!-- <span class="search"><img src="../../assets/image/search.png" alt="" /></span> -->
  </header>
</template>

<script>
export default {
  data() {
    return {
      tabs: [
        { name: "首页", link: "" },
        { name: "产品介绍", link: "product" },
        { name: "科技创新", link: "" },
        { name: "新闻动态", link: "" },
        { name: "联系我们", link: "about" },
      ],
    };
  },
  methods: {
    goHome() {
      this.$router.push({ path: "/" });
    },
    goLink(link) {
      this.$router.push({ path: `/${link}` });
    },
  },
};
</script>

<style lang="scss" scoped>
header {
  width: 90%;
  height: calc(100vw * 150 / 1920);
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 0 auto;
  font-family: "SourceHanSansCN-Medium";
  .logo {
    width: calc(100vw * 76 / 1920);
    height: calc(100vw * 104 / 1920);
    cursor: pointer;
  }
  .search {
    img {
      width: 70%;
    }
  }
  .header-tabs {
    width: 55%;
    margin-left: 20%;
    display: flex;
    justify-content: space-around;
    align-items: center;
    .tab {
      position: relative;
      font-weight: 400;
      font-style: normal;
      font-size: calc(100vw * 32 / 1920);
      line-height: 100%;
      cursor: pointer;
      padding-bottom: 7px;
    }
    .tab.active {
      color: #86c13e; /* 选中的颜色 */
      font-weight: bold; /* 选中的字体加粗 */
    }
    .tab::after {
      content: "";
      position: absolute;
      left: 50%; /* 初始位置在中间 */
      bottom: 0;
      width: 0; /* 初始隐藏 */
      height: 3px;
      background-color: #86c13e;
      transition: width 0.3s ease, left 0.3s ease; /* 同时动画宽度和左偏移 */
    }
    .tab:hover::after {
      width: 100%; /* 宽度铺满 */
      left: 0; /* 从中间移动到左侧，实现两边展开 */
    }
  }
}
</style>
