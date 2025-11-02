<template>
  <div>
    <div class="title1" :style="{ textAlign: isCenter ? 'center' : 'left' }">{{ title1 }}</div>
    <div class="title2" :style="{ textAlign: isCenter ? 'center' : 'left' }">{{ title2 }}</div>
  </div>
</template>

<script>
export default {
  props: {
    title1: String,
    title2: String,
    isCenter: {
      type: Boolean,
      default: false,
    },
  },
  data() {
    return {};
  },
};
</script>

<style lang="scss" scoped>
.title1 {
  font-family: 'SourceHanSansCN-Medium';
  font-weight: 500;
  font-size: calc(100vw*30/1920);
  line-height: 100%;
  position: relative;
  z-index: 2;
  margin-left: 3px;
}
.title2 {
  font-weight: 900;
  font-size: calc(100vw*48/1920);
  line-height: 100%;
  text-transform: uppercase;
  color: #4E9B4980;
  margin-top: -45px;
  opacity: 0.2;
}
</style>
