<template>
  <div class="banner" :style="{ backgroundImage: `url(${backgroundUrl})`, backgroundSize: 'cover' }">
    <div class="slogons">
      <div class="slogon1">{{ slogon1 }}</div>
      <div class="slogon2">{{ slogon2 }}</div>
    </div>
  </div>
</template>
<script>
export default {
  name: 'Banner',
  props: {
    slogon1: String,
    slogon2: String,
    backgroundUrl: String,
  },
};
</script>
<style lang="scss" scoped>
.banner {
  width: 100%;
  height: calc(100vw * (772 / 1920));
  font-family: 'SourceHanSansCN-Medium';
  .slogons {
    margin-left: 10%;
    padding-top: 28.5%;
  }
  .slogon1,
  .slogon2 {
    color: #fff;
    font-size: 48px;
    line-height: 100%;
  }
  .slogon1 {
    font-weight: 500;
    margin-bottom: 15px;
  }
  .slogon2 {
    font-weight: 900;
  }
}
</style>
