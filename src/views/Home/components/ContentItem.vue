<template>
  <div class="content-item">
    <Titles :title1="title1" :title2="title2" />
    <div class="content">{{ content }}</div>
  </div>
</template>

<script>
import Titles from "@/components/common/Titles.vue";
export default {
  components: {
    Titles,
  },
  props: {
    title1: String,
    title2: String,
    content: String,
  },
};
</script>

<style lang="scss" scoped>
.content-item {
  width: 100%;
  .content {
    font-family: 'SourceHanSansCN-Normal';
    font-weight: 500;
    font-style: Normal;
    font-size: calc(100vw*20/1920);
    line-height: calc(100vw*32/1920);
    letter-spacing: 32%;
     margin-top: 50px;
  }
}
</style>
