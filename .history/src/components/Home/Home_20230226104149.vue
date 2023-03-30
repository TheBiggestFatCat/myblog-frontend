<template>
  <div class="home">
    <Navigation></Navigation>
    <div class="home-top">
      <div class="avatar">
        <img :src="avatar" alt="Image">
      </div>
      <div class="avatar-right">
        <h2>{{ name }}</h2>
        <div class="border"></div>
        <p v-for="i in introduction" :key="i">{{ i }}</p>
        <a href="https://github.com/" target="_blank">
          <button><img src="@/assets/icons/github.svg" style="position: relative; top: 4px;" alt=""></button>
        </a>
        <a href="https://csdn.com/">
          <button><img src="@/assets/icons/csdn.svg" style="position: relative; top: 2px; width: 24px" alt=""></button>
        </a>
      </div>
    </div>
    <div class="home-body">
      <div class="personal">
        <h3></h3>
        <div class="border"></div>
        <!-- <p>{{ personalText }}</p> -->
      </div>
    </div>
  </div>
</template>

<script lang='ts' setup>
import Navigation from './Navigation.vue';
import { ref } from 'vue'

// 头像
const avatar = ref('src/assets/pics/avatar.jpg')

// 姓名
const name = '张齐煜'

// 顶部介绍
const introduction = [
  '一只来自外星的猫猫虫。',
]

</script>
 
<style lang="less" scoped>
.home-top {
  width: 100vw;
  height: 400px;
  align-items: center;
  display: flex;
  flex-flow: row nowrap;
  justify-content: center;

  .avatar {
    width: 300px;
    height: 200px;
    padding-right: 60px;

    img {
      width: 200px;
      height: 200px;
      border-radius: 50%;
    }
  }

  .avatar-right {
    width: 400px;
    height: 160px;

    h2 {
      font-size: 32px;
    }

    .border {
      margin: 20px 0 20px 0;
      width: 100%;
      border-top: 1px solid #000;
    }

    p {
      margin-bottom: 20px;
    }

    // github按钮
    button:nth-of-type(1) {
      background-color: #24292e;
      color: #fff;
      padding: 8px 30px;
      border: none;
      border-radius: 5px;
      font-size: 16px;
      cursor: pointer;
      transition: all .2s;
    }

    button:nth-of-type(1):hover {
      background-color: #3e4147;
    }

    // csdn按钮
    button:nth-of-type(2) {
      background-color: #d66639;
      color: #fff;
      padding: 8px 30px;
      border: none;
      border-radius: 5px;
      font-size: 16px;
      cursor: pointer;
      transition: all .2s;
      margin-left: 20px;
    }

    button:nth-of-type(2):hover {
      background-color: #d87d59;
    }
  }
}

.home-top::before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  width: 100vw;
  height: 400px;
  // width: 100%;
  // height: 100%;
  background-image: url(@/assets/pics/home3.jpg);
  background-position: 0 -400px;
  background-size: cover;
  filter: blur(2px);
  /* 设置模糊半径 */
  opacity: 0.85;
  /* 设置不透明度 */
  z-index: -1;
  /* 将遮罩层放在最底层 */
}

.home-body {
  height: 1000px;
  background-color: #d8d8d8;
}</style>