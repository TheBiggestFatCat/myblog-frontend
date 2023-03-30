<template>
  <div class="home">
    <div class="home-top">
      <div class="avatar">
        <img src="@/assets/pics/avatar.jpg" alt="">
      </div>
      <div class="avatar-right">
        <h2>张齐煜</h2>
        <div class="border"></div>
        <p>一些个人简介</p>
      </div>
    </div>
  </div>
</template>

<script lang='ts' setup>
</script>
 
<style lang="less" scoped>
.home-top {
  width: 100vwpx;
  height: 400px;
  align-items: center;
  display: flex;
  flex-flow: row nowrap;
  justify-content: center;
  .avatar {
    width: 300px;
    height: 200px;
    padding-right: 100px;
    img {
      width: 200px;
      height: 200px;
      border-radius: 50%;
    }
  }
  .avatar-right {
    width: 400px;
    height: 200px;
    color: #fff;
    h2 {
      font-size: 32px;
    }
    .border {
      width: 100%;
      border-top: 1px solid #fff;
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
  background-image: url(@/assets/pics/home1.jpg);
  // background-position: 0 -200px;
  background-size: cover;
  filter: blur(2px); /* 设置模糊半径 */
  opacity: 0.85; /* 设置不透明度 */
  z-index: -1; /* 将遮罩层放在最底层 */
}
</style>