<template>
  <div class="blog_layout">
    <Header />
    <main>
      <RouterView />
    </main>
    <Footer />
  </div>
</template>

<script lang="ts" setup>
import { RouterView } from 'vue-router'
import Header from "@/components/header"
import Footer from "@/components/footer"
</script>

<style>
  .blog_layout {
    width: 100%;
    height: 100%;
    overflow: auto;
    background-color: #000000;
    color: #ffffff;
  }
</style>