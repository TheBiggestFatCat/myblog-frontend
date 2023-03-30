<template>
  <nav :class="{'bg-white': !isTop, 'bg-blur': isTop}">
      <div class="logo">小怪兽的神秘山洞</div>
        <div class="ui">
          <div>个人介绍</div>
          <div>项目经历</div>
          <div>专业能力</div>
        </div>
  </nav>
</template>

<script lang="ts">
import { onMounted, onUnmounted, ref } from 'vue'

export default {
  name: 'Navigation',

  setup() {
    const isTop = ref(true)

    const handleScroll = () => {
      isTop.value = window.pageYOffset === 0
    }

    onMounted(() => {
      window.addEventListener('scroll', handleScroll)
    })

    onUnmounted(() => {
      window.removeEventListener('scroll', handleScroll)
    })

    return { isTop }
  }
}
</script>

<style lang="less" scoped>
nav {
  position: fixed;
  height: 64px;
  top: 0;
  left: 0;
  right: 0;
  padding: 0 20px 0 20px;
  transition: background-color 0.3s ease-in-out;
  display: flex;
  justify-content: space-between;
  align-items: center;
}


.logo {
  font-weight: bold;
  font-size: 24px;
}

.ui {
  display: flex;
  list-style: none;
  margin: 0;
  padding: 0;
  height: 100%;
  div {
    position: relative;
    display: flex;
    align-items: center;
    margin-left: 20px;
    height: 100%;
    cursor: pointer;
  }

  div::before {
    content: "";
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    opacity: 0;
    background-color: rgba(0, 0, 0, 0.5); /* 半透明的灰色背景 */
    transition: opacity 0.3s ease;
  }

  div:hover::before {
  opacity: 0.3;
}
}



.bg-white {
  background-color: white;
}

.bg-blur {
  background-color: rgba(255, 255, 255, 0.198);
  backdrop-filter: blur(10px);
}
</style>
