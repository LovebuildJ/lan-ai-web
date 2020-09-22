<template>
  <!-- 主容器 -->
  <el-container>
    <!-- 页面头部 -->
    <el-header>
      <el-row>
        <el-col :span="2">
          <div class="grid-content bg-purple">
            <el-link type="primary">LANGUAGE-AI</el-link>
          </div>
        </el-col>
        <el-col :span="14">
          <div class="grid-content bg-purple"></div>
        </el-col>
        <el-col :span="8">
          <div class="grid-content bg-purple">
            <!-- 导航菜单 -->
            <el-menu
              :default-active="activeIndex2"
              class="el-menu-demo"
              mode="horizontal"
              @select="handleSelect"
              background-color="#545c64"
              text-color="#fff"
              active-text-color="#ffd04b"
            >
              <el-menu-item index="1">首页</el-menu-item>
              <el-menu-item index="2">在线使用</el-menu-item>
              <el-menu-item index="3">在线文档</el-menu-item>
              <el-menu-item index="4">源码商城</el-menu-item>
              <el-menu-item index="5">关于作者</el-menu-item>
            </el-menu>
            <!-- nav menu end -->
          </div>
        </el-col>
      </el-row>
    </el-header>
    <!--  header end  -->

    <el-main>
      <!-- 走马灯 -->
      <el-carousel :interval="5000" arrow="always">
        <el-carousel-item v-for="item in imgs" :key="item">
          <el-image :src="item"></el-image>
        </el-carousel-item>
      </el-carousel>
      <el-divider content-position="center">AI伪原创NLP应用类先驱</el-divider>
      <h3>产品列表</h3>
      <!-- Card 卡片 -->
      <el-row :gutter="12">
        <el-col :span="8">
          <el-card shadow="always">总是显示</el-card>
        </el-col>
        <el-col :span="8">
          <el-card shadow="hover">鼠标悬浮时显示</el-card>
        </el-col>
        <el-col :span="8">
          <el-card shadow="never">从不显示</el-card>
        </el-col>
      </el-row>
    </el-main>
    <el-footer>Footer</el-footer>
  </el-container>
</template>

<script>
export default {
  data() {
    return {
      activeIndex: "1",
      activeIndex2: "1",

      imgs: [
        require("./assets/logo_1.png"),
        require("./assets/logo_3.png"),
        require("./assets/logo_2.png"),
      ],
    };
  },
  methods: {
    handleSelect(key, keyPath) {
      console.log(key, keyPath);
    },
  },
};
</script>

<style>
/* 
  布局容器
 */
.el-header {
  background-color: #545c64;
  color: #545c64;
  text-align: center;
  line-height: 60px;
  padding: 0 0px;
}

.el-main {
  background-color: #e9eef3;
  color: #333;
  text-align: center;
  /* height: 750px; */
  padding: 0px;
}

.el-footer {
  background-color: #b3c0d1;
  color: #333;
  text-align: center;
  line-height: 60px;
  padding: 0 0px;
}
/* 
  导航布局
 */
.el-row {
  margin-bottom: 20px;
}
.el-col {
  border-radius: 4px;
}
.bg-purple-dark {
  background: #99a9bf;
}
.bg-purple {
  background: #545c64;
}
.bg-purple-light {
  background: #e5e9f2;
}
.grid-content {
  min-height: 62px;
}
.row-bg {
  padding: 10px 0;
  background-color: #f9fafc;
}
/* 文字链接  */
.el-link {
  font-size: 16px;
  font-family: "Courier New", Courier, monospace;
}

/*  走马灯  */
.el-carousel__container {
  height: 740px;
}

.el-carousel__item h3 {
  color: #475669;
  font-size: 18px;
  opacity: 0.75;
  margin: 0;
}

.el-carousel__item:nth-child(2n) {
  background-color: #99a9bf;
}

.el-carousel__item:nth-child(2n + 1) {
  background-color: #d3dce6;
}

/* 跑马灯图片 */
.el-image {
  width: 100%;
  height: 100%;
}

/* 分割线 */
.el-divider__text {
  background: rgba(255, 255, 255, 0);
}
</style>
