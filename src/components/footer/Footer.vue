<template>
  <footer class="blog_footer">
    <div class="blog_footer_license">
      ©2020 - 2023 By SoulReader
    </div>
    <div class="blog_footer_timer">
      当前时间：{{ datetime }}
    </div>
    <div class="blog_footer_detail">
      Framework Vue4
    </div>
  </footer>
</template>

<script lang="ts" setup>
import { ref } from 'vue';

const datetime = ref("")

const getCurrent = () => {
  const date = new Date()
  const day = date.toLocaleDateString().replace(/\//g, "-")
  const timer = date.toLocaleTimeString()
  datetime.value = `${day} ${timer}`
  setTimeout(getCurrent, 1000)
}
getCurrent()
</script>

<style lang="scss">
  .blog_footer {
    width: 100%;
    height: 100px;
    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    align-items: center;
    align-content: center;
    overflow: hidden;

    > div {
      margin-top: 8px;
    }
  }
</style>
