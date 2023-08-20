<template>
  <div class="blog_banner">
    <BannerImage />
    <div class="blog_banner_text">
      <div>
        <span>SOULREADER</span>
        <span>快乐小菜鸟</span>
      </div>
    </div>
  </div>
</template>

<script lang="ts" setup>
import BannerImage from './BannerImage.vue';
</script>

<style lang="scss">
  .blog_banner {
    width: 100%;
    height: calc(100vh - 60px);
    position: relative;

    &_text {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      display: flex;
      justify-content: space-around;
      align-items: center;
      align-content: center;

      > div {
        display: flex;
        flex-direction: column;
        justify-content: flex-start;
        align-items: center;
        align-content: center;
      }
    }
  }
</style>
