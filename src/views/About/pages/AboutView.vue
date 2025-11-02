<template>
  <div class="about">
    <Banner :slogon1="slogon1" :slogon2="slogon2" :backgroundUrl="backgroundUrl" />
    <img src="../../../assets/image/address.jpg" alt="" />
    <div class="card">
      <div class="card-left">
        <Titles :title1="title1" :title2="title2" />
        <div class="content left-content">{{ content }}</div>
      </div>
      <div class="card-right">
        <div class="right-item" v-for="value in rightItems">
          <img class="icon" :src="value.url" alt="" />
          <span class="content right-content">{{ value.content }}</span>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import Banner from "../../../components/common/Banner.vue";
import Titles from "@/components/common/Titles.vue";
export default {
  components: {
    Banner,
    Titles,
  },
  data() {
    return {
      slogon1: "盾护沃野 共享未来",
      slogon2: "SHIELD THE FIELDS SHARE THE FUTURE",
      backgroundUrl: "../../../assets/image/banner-about.jpg",
      title1: "联系我们",
      title2: "CONTACT",
      content: "欢迎与我们取得联系，我们将竭诚为您服务",
      rightItems: [
        { url: "/src/assets/image/dingwei.jpg", content: "来访定位：" },
        { url: "/src/assets/image/email.jpg", content: "邮件联系：@Henan Shield Agrotech Co., Ltd." },
      ],
    };
  },
};
</script>
<style scoped lang="scss">
.about {
  width: 100%;
  font-family: 'SourceHanSansCN-Normal';
  img {
    width: 80%;
    height: auto;
    display: block;
    margin: 0 auto;
    margin-top: 50px;
    position: relative;
    z-index: -1;
  }
  .card {
    width: 70%;
    height: calc(70vw * 265 / 1184);
    margin: 0 auto;
    margin-top: -100px;
    margin-bottom: 150px;
    padding: 0 5%;
    display: flex;
    justify-content: space-between;
    align-items: center;
    box-shadow: 0px 4px 11.9px 3px #0000001a;
    background-color: #fff;
    .content {
      font-weight: 500;
      font-style: Normal;
      font-size: calc(100vw * 20 / 1920);
      line-height: 100%;
      color: #323232;
    }
    .card-left {
      width: 50%;
      .left-content {
        margin-top: 50px;
      }
    }
    .card-right {
      width: 50%;
      height: 40%;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
      .right-item {
        .icon {
          width: calc(100vw*28/1920);
          height: auto;
          margin: 0;
          margin-right: 20px;
          display: inline-block;
          vertical-align: middle;
          box-sizing: border-box;
          position: relative;
          z-index: 1;
        }
        .right-content {
          display: inline-block;
          vertical-align: middle;
          box-sizing: border-box;
        }
      }
    }
  }
}
</style>
