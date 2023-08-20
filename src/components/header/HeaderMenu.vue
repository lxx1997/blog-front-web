<template>
  <div class="blog_header_menu">
    <div class="menu">
      <div class="menu_item" v-for="menu in menuList" :key="menu.title">
        <RouterLink :to="menu.path">{{ menu.title }}</RouterLink>
      </div>
    </div>
  </div>
</template>

<script lang="ts" setup>
import { RouterLink } from 'vue-router';

const menuList = [
  {
    path: "/",
    title: "首页"
  },
  {
    path: "/category",
    title: "分类"
  },
  {
    path: "/tags",
    title: "标签"
  },
  {
    path: "/archive",
    title: "时间线"
  }
]
</script>

<style lang="scss">
  
</style>
