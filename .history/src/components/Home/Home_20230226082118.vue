<template>
  <div class="home">
    aaa
  </div>
</template>

<script lang='ts' setup>
</script>
 
<style lang="less" scoped>
.home {
  width: 1000px;
  height: 400px;
  background-image: url(@/assets/pics/home1.jpg);
  background-size: cover;
  background-position: 0 -200px;
  backdrop-filter: blur(10px);
}

// .home::before {
//   content: "";
//   position: fixed;
//   top: 0;
//   left: 0;
//   width: 100vw;
//   height: 400px;
//   // width: 100%;
//   // height: 100%;
//   background-image: url(@/assets/pics/home1.jpg);
//   background-size: cover;
//   filter: blur(4px); /* 设置模糊半径 */
//   opacity: 0.5; /* 设置不透明度 */
//   z-index: -1; /* 将遮罩层放在最底层 */
// }
</style>