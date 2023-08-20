<template>
  <header class="blog_header">
    <HeaderLeft />
    <HeaderMenu />
  </header>
</template>

<script lang="ts" setup>
import HeaderLeft from "./HeaderLeft.vue"
import HeaderMenu from "./HeaderMenu.vue"
</script>

<style lang="scss">
  .blog_header {
    width: 100%;
    height: 60px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    align-content: center;
    background-color: #fff;
    color: #000;

    &_left {
      margin-left: 40px;
      span {
        font-size: 30px;
        color: #333;
        font-weight: bold;
        font-style: italic;
      }
    }

    &_menu {
      margin-right: 24px;
      .menu {
        display: flex;
        justify-content: flex-start;
        
        &_item {
          padding: 6px 12px;
          cursor: pointer;
          position: relative;

          &::after {
            content: "";
            display: inline-block;
            width: 0px;
            height: 3px;
            background: #2c7dfa;
            position: absolute;
            bottom: 0;
            left: 0;
            transition: width 0.3s linear;
          }

          &.active, &:hover {

            &::after {
              content: "";
              width: 100%;
              transition: width 0.3s linear;
            }
          }
        }
      }
    }
  }
</style>
