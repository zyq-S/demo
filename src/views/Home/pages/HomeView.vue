<template>
  <div class="home">
    <Banner :slogon1="slogon1" :slogon2="slogon2" :backgroundUrl="backgroundUrl" />
    <main>
      <div class="introduce">
        <div class="company-introduce">
          <div class="company-left">
            <ConrenrtItem :title1="title1" :title2="title2" :content="content1" />
            <div class="learn-more">了解更多<i></i></div>
          </div>
          <img src="/src/assets/image/company-img.jpg" alt="" />
        </div>
        <div class="paten-introduce">
          <img src="/src/assets/image/patent.jpg" alt="" />
          <div class="paten-right">
            <ConrenrtItem :title1="title3" :title2="title4" :content="content2" />
            <div class="learn-more">了解更多<i></i></div>
          </div>
        </div>
        <div class="certificate"><img src="/src/assets/image/certification.jpg" alt="" /></div>
      </div>
      <div class="share">
        <Titles :title1="shareTitle1" :title2="shareTitle2" :isCenter="true" />
        <div class="share-cards">
          <div
            class="share-card"
            v-for="value in cards"
            :style="{ backgroundImage: `url(${value.url})` }"
          >
            <div class="card-title">{{ value.title }}</div>
          </div>
        </div>
        <div class="learn-more" style="text-align: center">了解更多</div>
      </div>
      <div class="company-information">
        <div class="information-left">
          <Titles :title1="informationTitle1" :title2="informationTitle2" />
          <div class="address">办公地址：</div>
          <div class="contact">联系合作：</div>
          <div class="learn-more">了解更多<i></i></div>
        </div>
        <div class="information-right">
          <img src="/src/assets/image/company2.jpg" alt="" />
        </div>
      </div>
    </main>
  </div>
</template>
<script>
import Banner from "../../../components/common/Banner.vue";
import ConrenrtItem from "../components/ContentItem.vue";
import Titles from "@/components/common/Titles.vue";
export default {
  name: "HomeView",
  components: {
    Banner,
    ConrenrtItem,
    Titles,
  },
  data() {
    return {
      slogon1: "盾护沃野 共享未来",
      slogon2: "SHIELD THE FIELDS SHARE THE FUTURE",
      backgroundUrl: "/src/assets/image/banner-home.jpg",
      title1: "企业介绍",
      title2: "INTRODUCTION",
      shareTitle1: "案例分享",
      shareTitle2: "CASE SHARING",
      informationTitle1: "企业信息",
      informationTitle2: "INFORMATION",
      cards: [
        { title: "组合方案", url: "/src/assets/image/anli-1.jpg" },
        { title: "水稻杂草", url: "/src/assets/image/anli-2.jpg" },
        { title: "虫害案例", url: "/src/assets/image/anli-3.jpg" },
        { title: "病害案例", url: "/src/assets/image/anli-4.jpg" },
      ],
      content1:
        "河南盾护农业科技是一家创新的作物保护企业，依托中国完善的供应链体系服务全球农化市场。公司拥有3座现代化制剂工厂、300多个中国农药登记证ICAMA，员工总数超过500人。我们专注于农药制剂生产、出口与综合解决方案的提供，通过合规高效的解决方案帮助客户缩短市场准入时间、降低采购成本。凭借研发创新与绿色生产实力，盾护科技正成为全球农户和合作伙伴值得信赖的植保伙伴。",
      title3: "专利介绍",
      title4: "PATENT",
      content2:
        "河南盾护农业科技是一家创新的作物保护企业，依托中国完善的供应链体系服务全球农化市场。公司拥有3座现代化制剂工厂、300多个中国农药登记证ICAMA，员工总数超过500人。我们专注于农药制剂生产、出口与综合解决方案的提供，通过合规高效的解决方案帮助客户缩短市场准入时间、降低采购成本。凭借研发创新与绿色生产实力，盾护科技正成为全球农户和合作伙伴值得信赖的植保伙伴。",
    };
  },
};
</script>
<style scoped lang="scss">
main {
  width: 80%;
  margin: 0 auto;
  margin-bottom: 100px;
  font-family: 'SourceHanSansCN-Medium';
  .learn-more {
    font-weight: 500;
    font-style: Medium;
    font-size: calc(100vw * 20 / 1920);
    line-height: 100%;
    letter-spacing: 0%;
    text-decoration: underline;
    text-decoration-style: solid;
    margin-top: 30px;
    color: #323232;
    i {
      display: inline-block;
      width: calc(100vw * 16 / 1920);
      height: calc(100vw * 16 / 1920);
      background-image: url("/src/assets/image/arrow-right-green.png");
      background-size: contain;
      background-repeat: no-repeat;
      margin-left: calc(100vw * 10 / 1920);
      vertical-align: middle;
    }
  }
  .introduce {
    position: relative;
    .company-introduce {
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin-top: 50px;
      .company-left {
        width: 45%;
      }
      img {
        width: 50%;
        height: auto;
      }
    }
    .paten-introduce {
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin-top: 100px;
      img {
        width: 50%;
        height: auto;
      }
      .paten-right {
        width: 45%;
      }
    }
  }
  .certificate {
    position: absolute;
    bottom: -10%;
    transform: translate(120%, 0%);
    img {
      border-radius: 50%;
      width: calc(100vw * 406 / 1920);
      height: auto;
    }
  }
  .share {
    margin-top: 150px;
    .share-title {
      display: flex;
      justify-content: center;
      align-items: center;
      .share-title-one {
        width: calc(100vw * 8 / 1920);
        height: calc(100vw * 4 / 1920);
        background-color: #4e9b49;
        border-radius: calc(100vw * 2 / 1920);
      }
      .share-title-two {
        font-weight: 600;
        font-size: calc(100vw * 36 / 1920);
        line-height: 100%;
        color: #323232;
        margin-left: 20px;
      }
    }
    .share-cards {
      display: flex;
      justify-content: space-between;
      flex-wrap: wrap;
      align-items: center;
      margin-top: 50px;
      .share-card {
        width: calc(100vw * 742 / 1920);
        height: calc(100vw * 348 / 1920);
        border-radius: 30px;
        background-size: cover;
        background-repeat: no-repeat;
        position: relative;
        margin-bottom: 20px;
        .card-title {
          width: 100%;
          height: calc(100vw * 60 / 1920);
          position: absolute;
          bottom: 0;
          background: #00000080;
          border-radius: 0 0 30px 30px;
          font-weight: 500;
          font-size: calc(100vw * 26 / 1920);
          line-height: 250%;
          color: #fff;
          text-align: center;
        }
      }
    }
  }
  .company-information {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-top: 150px;
    .information-left {
      width: 45%;
      .address,
      .contact {
        font-weight: 400;
        font-style: Regular;
        font-size:calc(100vw*20/1920);
        line-height: 32px;
        margin-top: 50px;
      }
    }
    .information-right {
      width: 50%;
      img {
        width: 100%;
        height: auto;
      }
    }
    .learn-more {
      margin-top: 130px;
    }
  }
}
</style>
