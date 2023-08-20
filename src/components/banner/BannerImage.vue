<template>
  <!-- 图片特效 -->
  <div class="image_filter">
    <div v-for="number of splitNumber" :key="number" :class="`filter_item filter_box${number}`" :style="{
      width: `${percent}%`
    }"></div>
  </div>
</template>

<script lang="ts" setup>
import { ref, onMounted } from 'vue';

import BannerImage1 from "@/assets/img/14536054.jpg"
import BannerImage2 from "@/assets/img/49170305_p0.jpg"

const splitNumber = ref(5)
const percent = (1 / splitNumber.value) * 100;
onMounted(() => {
  const filterItems = document.getElementsByClassName("filter_item")
  console.log(filterItems, filterItems.length)
  for(let i = 0; i < filterItems.length; i++) {
    const div = document.createElement("div")
    div.style.background = `url(${BannerImage1})`
    div.style.backgroundSize = "cover"
    div.style.backgroundPositionX = `${i * percent}%`
    const div2 = document.createElement("div")
    div2.style.background = `url(${BannerImage2})`
    div2.style.backgroundSize = "cover"
    div2.style.backgroundPositionX = `${i * percent}%`
    filterItems[i].appendChild(div)
    filterItems[i].appendChild(div2)
  }
  // setTimeout(() => {
  //   for(let i = 0; i < filterItems.length; i++) {
  //     const item = filterItems[i]
  //     item.classList.add("rotate")
  //   }
  // }, 2000)
})
</script>

<style lang="scss">
.image_filter {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: flex-start;

  .filter_item {
    height: 100%;
    position: relative;

    > div {
      position: absolute;
      width: 100%;
      height: 100%;
    }

    &>div:nth-child(1) {
      z-index: 1
    }

    &.rotate {
      transform: rotateY(180deg);
      transition: transform 2s linear;

      &>div:nth-child(1) {
        z-index: 0
      }

      &>div:nth-child(2) {
        z-index: 1;
      }
    }
  }
}
</style>
