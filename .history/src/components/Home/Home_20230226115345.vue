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
      <!-- 个人介绍 -->
      <div class="personal">
        <h3>个人介绍</h3>
        <div class="border"></div>
        <p v-for="i in personalText">{{ i }}</p>
      </div>
      <!-- 项目经历 -->
      <div class="project">
        <h3>项目经历</h3>
        <div class="border"></div>
        <div class="project-bg" v-for="i in project">
          <img :src="i.img" alt="Image">
          <div class="right">
            <p class="title"></p>
            <p class="text"></p>
            <p class="date"></p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang='ts' setup>
import Navigation from './Navigation.vue';
import { ref } from 'vue'

// 头部

// 头像
const avatar = 'src/assets/pics/avatar.jpg'

// 姓名
const name = '张齐煜'

// 顶部介绍，允许多行
const introduction = [
  '一只来自外星的猫猫虫。',
]

// 头部以下

// 个人介绍，允许多行
const personalText = [
  '你好，让我来介绍一下：他是理想成为一名全栈程序员的小（大）可爱，张齐煜。实名上网的感觉，还是不太习惯呢。(๑•́ ₃ •̀๑)',
  '就是写这个网站的人，有着还算活泼开朗的性格，善于表达，所以人缘一直很好，也当过老师哦。（诶嘿~(✿◡‿◡)）',
  '别人说这个人挺机灵的，秋游的时候批发饮料到车上和景区倒卖，虽然现在看看挺傻的。不过大学里和同学一起做点项目也赚了一点小钱，这比小时候犯傻赚的多多了吧。',
  '他真的是很喜欢计算机的，这个愣头青高考志愿所有学校只填了计算机专业。不过现在看来他真的学的真的开心，专业课也全是高分。他的B站首页也一直给他推计算机有关的视频，对这个领域的最新技术，他还是很关注的。',
  '',
  '他入校以来一直积极参与Steam编程社团的活动，在大二的时候还在社团中当了几次讲师，给学弟学妹讲讲python的基础语法之类的。说到讲课，之前实习的时候还当给小学生讲python的老师哦。',
  '之前担任数据科学双创社的社长，参与团队项目，负责python爬虫和前端网页的开发。虽然关于python，爬虫什么的现在已经好久不做了，但说不定待他精通JS后还会回去看看呢？',
  '通常在项目中担任组长，组织完成期末小组作业、参加双创赛、三创赛的项目等。没错，接活的时候还要天天和客户对线，但这就是领导的职责嘛。',
  '英语水平虽然不怎么样但还是过了CET4，并且熟练使用谷歌翻译、有道词典、百度翻译。普通话还是挺标准的，上海话也不是洋泾浜（哈哈）。',
  '下面介绍专业技能，咳咳。他熟悉HTML、CSS、JS(ES6)等web开发语言，能够使用VUE2/VUE3编写组件参与项目（这个网站就是vue写的），以及微信小程序开发（赚了不少钱）。了解REACT等其他框架（还是最喜欢VUE），能够使用node.js进行后端开发，包括express框架，mySQL（没错这些也是网站的组成部分之一）。熟练使用git进行团队协作开发。熟练使用office办公软件以及邮箱等常用工具。'
]

// 项目经历

const project = [
  {
    img: 'src/assets/pics/project1.png',
    title: '项目1',
    text: '这是一个项目，不过是假数据而已。',
    date: '2023/2/26 - 2023/2/27'
  },
  {
    img: 'src/assets/pics/project2.png',
    title: '项目2',
    text: '这是一个项目，不过是假数据而已。',
    date: '2023/2/26 - 2023/2/27'
  },
  {
    img: 'src/assets/pics/project3.png',
    title: '项目3',
    text: '这是一个项目，不过是假数据而已。',
    date: '2023/2/26 - 2023/2/27'
  },
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
// 头部以下
.home-body {
  height: 1000px;
  background-color: #d8d8d8;
  // 个人介绍
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
    p {
      line-height: 200%;
    }
  }
  // 项目经历
  .project {
    background-color: #f3f3f3;
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
    p {
      line-height: 200%;
    }
    .project-bg {
      display: flex;
      flex-flow: row nowrap;
      justify-content: center;
      align-items: center;
      margin: 100px 0 100px 0 ;
      width: 70vw;
      height: 500px;
      background-color: #fff;
      border-radius: 10px;
      box-shadow: 0 0 20px rgba(1, 1, 1, 0.33);
      img {
        width: 400px;
        height: 260px;
      }
      .right {
        width: ;
      }
    }
  }


}
</style>