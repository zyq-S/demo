<template>
  <div class="product">
    <Banner :slogon1="slogon1" :slogon2="slogon2" :backgroundUrl="backgroundUrl" />
    <main>
      <div class="top">
        <Titles :title1="title1" :title2="title2" />
        <div class="search">
          <img class="icon" src="/src/assets/image/search-icon.png" alt="" /><span>按类别筛选</span>
        </div>
      </div>
      <div class="list">
        <div class="list-title">
          <div class="type">类别</div>
          <div class="name">成分及含量</div>
          <div class="pd">PD证号</div>
        </div>
        <div class="list-item" v-for="(value, index) in paginatedData" :key="index">
          <div class="type">{{ value.type }}</div>
          <div class="name">{{ value.include }}</div>
          <div class="pd">{{ value.pd }}</div>
        </div>
        <div class="block">
          <el-pagination
            layout="prev, pager, next"
            :total="listData.length"
            :page-size="pageSize"
            v-model:current-page="currentPage"
            class="el-pagination"
          />
        </div>
      </div>
    </main>
  </div>
</template>

<script>
import Banner from "../../../components/common/Banner.vue";
import Titles from "@/components/common/Titles.vue";
import listData from "../existing_certificates.json";
import { ElPagination } from "element-plus";

export default {
  name: "ProductView",
  components: {
    Banner,
    Titles,
    ElPagination,
  },
  data() {
    return {
      slogon1: "盾护沃野 共享未来",
      slogon2: "SHIELD THE FIELDS SHARE THE FUTURE",
      backgroundUrl: new URL("/src/assets/image/banner-product.jpg", import.meta.url).href,
      title1: "快速查寻",
      title2: "SEARCH",
      listData: listData,
      currentPage: 1,
      pageSize: 10,
    };
  },
  computed: {
    paginatedData() {
      const start = (this.currentPage - 1) * this.pageSize;
      const end = start + this.pageSize;
      return this.listData.slice(start, end);
    },
  },
};
</script>

<style scoped lang="scss">
main {
  width: 80%;
  margin: 0 auto;
  margin-bottom: 100px;
  font-family: "SourceHanSansCN-Medium";
  .top {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-top: 50px;
  }
  .search {
    width: calc(100vw * 288 / 1920);
    height: calc(100vw * 60 / 1920);
    border: 2px solid #4e9b49;
    border-radius: 90px;
    display: flex;
    align-items: center;
    img {
      width: calc(100vw * 36 / 1920);
      height: auto;
      margin: 0 20px;
      box-sizing: border-box;
      display: inline-block;
      vertical-align: middle;
    }
    span {
      font-weight: 400;
      font-style: Regular;
      font-size: calc(100vw * 30 / 1920);
      line-height: 100%;
      color: #4e9b49;
      box-sizing: border-box;
      vertical-align: middle;
    }
  }
  .list {
    width: 100%;
    height: calc(100vw * 800 / 1920);
    border: 2px solid #d9d9d9;
    border-top: none;
    border-radius: 20px;
    margin-top: 50px;
    .list-title,
    .list-item {
      display: flex;
      justify-content: space-between;
      align-items: center;
      text-align: center;
      line-height: 100%;
      .type {
        width: 30%;
      }
      .name {
        width: 40%;
      }
      .pd {
        width: 30%;
      }
    }
    .list-item {
      height: calc(100vw * 60 / 1920);
      font-size: calc(100vw * 24 / 1920);
    }
    .list-title {
      height: calc(100vw * 80 / 1920);
      font-size: calc(100vw * 28 / 1920);
      font-weight: 600;
      color: #fff;
      background-color: #43944c;
      border-radius: 20px 20px 0 0;
      border: 2px solid #43944c;
    }
  }
  .block {
    width: fit-content;
    margin: 0 auto;
    margin-top: 20px;
    ::v-deep(.el-pager .is-active,--el-pagination-hover-color .--el-pagination-hover-color) {
      color: #4e9b49;
    }
    ::v-deep(.el-pager:hover) {
      color: #4e9b49;
    }
    ::v-deep(.el-icon:hover) {
      color: #4e9b49;
    }
    ::v-deep(.el-pagination__next:hover, .el-pagination__prev:hover) {
      color: #4e9b49;
    }
  }
}
</style>
