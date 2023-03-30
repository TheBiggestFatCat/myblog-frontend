<template>
  <div class="home">
    <!-- 导航栏 -->
    <Navigation></Navigation>

    <!-- 头部 -->
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
        <a href="https://blog.csdn.net/" target="_blank">
          <button><img src="@/assets/icons/csdn.svg" style="position: relative; top: 2px; width: 24px" alt=""></button>
        </a>
      </div>
    </div>

    <!-- 头部以下 -->
    <div class="home-body">
      <div class="personal">
        <h3>个人介绍</h3>
        <div class="border"></div>
        <p v-for="i in personalText">{{ i }}</p>
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

// 顶部介绍，允许多行
const introduction = [
  '一只来自外星的猫猫虫。',
]

// 头部以下

// 个人介绍
const personalText = [
  '性格开朗，善于表达，对于计算机专业方面的知识保持高度的敏感与注意力。在校学习期间，培养了良好的刻苦精神，能够利用广阔的互联网获取资料帮助自己学习与完成任务。有团队意识并且有一定领导能力，责任心强。注重团队沟通，并在此基础上高效率达成目标。兴趣广泛，爱好围棋、桌游等棋牌类运动、乒乓球。热爱音乐，考取过萨克斯十级证书。对美术也很有兴趣，学习过素描。',
  '自入校以来一直积极参与Steam编程社团的活动，在社团中作为讲师进行Python编程语言的入门教学与讲解。担任数据科学双创社的副社长，参与团队项目，负责python爬虫和前端网页的开发。通常在项目中担任组长，组织完成期末小组作业、参加双创赛、三创赛的项目等。参加软件开发俱乐部，正在参与学校组织的项目。独立使用云服务器部署过个人网站。',
  '英语CET4熟悉HTML、CSS、JS(ES6)等web开发语言，能够使用VUE编写组件参与项目，以及微信小程序开发。了解REACT等其他框架。能够简单使用node.js进行后端开发，使用过express框架，掌握基本的SQL语句。熟练使用git进行团队协作开发。熟练使用Python基础语法，在此基础上可以编写可视化、爬虫等项目。了解linux操作系统，使用过Xshell远程操作过centOS并独立部署过个人网站。熟练使用office办公软件以及邮箱等常用工具。'
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
    a:nth-of-type(1) button {
      background-color: #24292e;
      color: #fff;
      padding: 8px 30px;
      border: none;
      border-radius: 5px;
      font-size: 16px;
      cursor: pointer;
      transition: all .2s;
    }

    a:nth-of-type(1) button:hover {
      background-color: #3e4147;
    }

    // csdn按钮
    a:nth-of-type(2) button{
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

    a:nth-of-type(2) button:hover {
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

  .personal {
    background-color: #fff;
    padding: 50px 10vw 50px 10vw;
    h3 {
      font-size: 32px;
      color: #2376c8;
    }
    .border {
      width: 100%;
      margin: 20px 0 20px 0;
      border-top: 1px solid #000;
    }
  }


}
</style>