<template>
  <nav :class="{'bg-white': isTop, 'bg-blur': !isTop}">
    <div class="container">
      <div class="logo">小怪兽的神秘山洞</div>
        <div class="ui">
          <div>个人介绍</div>
          <div>项目经历</div>
          <div>专业能力</div>
        </div>
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
  padding: 20px;
  transition: background-color 0.3s ease-in-out;
}

.container {
  height: 100%;
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
    margin-left: 20px;
    height: 100%;
  }

  div:hover {
    background-color: #eaeaea;
  }
}



/* 顶部不透明白色背景 */
.bg-white {
  background-color: white;
}

/* 非顶部模糊透明背景 */
.bg-blur {
  background-color: rgba(255, 255, 255, 0.444);
  backdrop-filter: blur(10px);
}
</style>
