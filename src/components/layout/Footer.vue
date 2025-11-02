<template>
  <footer>
    <div class="footer-main">
      <img src="../../assets/image/logo-footer.png" alt="" :width="`100vw*${168/1920}`" />
      <div class="quick-link">
        <div class="link-title">{{ linkTitle }}</div>
        <div class="links">
          <a class="link" :href="`/${value.link}`" v-for="value in links">{{ value.name }}</a>
        </div>
      </div>
      <div class="address">
        <div class="address-title">{{ addressTitle }}</div>
        <div class="phone-num">{{ phoneNum }}</div>
        <div class="email">{{ email }}</div>
      </div>
    </div>
  </footer>
</template>

<script>
export default {
  data() {
    return {
      linkTitle: "快速导航",
      links: [
        { name: "首页", link: "" },
        { name: "产品介绍", link: "product" },
        { name: "科技创新", link: "" },
        { name: "新闻动态", link: "" },
        { name: "联系我们", link: "about" },
      ],
      addressTitle: "具体地理位置",
      email: "@Henan Shield Agrotech Co., Ltd.",
      phoneNum: "(+86)1688888888",
    };
  },
};
</script>

<style lang="scss" scoped>
footer {
  width: 100%;
  height: calc(100vw * 448 / 1920);
  display: flex;
  align-items: center;
  background: #43944C;
  background-image: url("../../assets/image/footer-bg.png");
  background-size:cover;
  font-family: 'SourceHanSansCN-Medium';
  .footer-main {
    width: 80%;
    display: flex;
    align-items: center;
    margin-left: 10%;
    .quick-link {
      width: calc(100% * 240 / 1920);
      margin-left: 25%;
      color: #fff;
      .link-title {
        font-size: 28px;
        font-weight: bolder;
        margin-bottom: 30px;
      }
      .links {
        display: flex;
        flex-direction: column;
        .link {
          width: 100%;
          text-decoration: none;
          font-size: 18px;
          font-weight: 500;
          color: #fff;
          position: relative;
          margin-bottom: 20px;
          padding-left: 25px;
        }
        .link::before {
          content: "";
          position: absolute;
          left: 0px;
          top: 45%;
          border: 1px solid #9bdf49;
          background-color: #9bdf49;
          display: inline-block;
          width: 8px;
          height: 8px;
          border-radius: 50%;
        }
      }
    }
    .address {
      margin-left: 10%;
      .address-title {
        color: #fff;
        font-size: 16px;
      }
      .phone-num {
        color: #fff;
        font-size: 32px;
        font-weight: bolder;
        margin: 15px 0;
      }
      .email {
        font-size: 24px;
        color: #9bdf49;
      }
    }
  }
}
</style>
