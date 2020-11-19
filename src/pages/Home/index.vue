<template>
  <div class="home-page">
    <el-container>
      <!-- aside导航 -->
      <el-aside width="200px">
        <h1 class="logo"></h1>
        <el-radio-group v-model="isCollapse" style="margin-bottom: 20px;">
          <!-- <el-radio-button :label="false">展开</el-radio-button>
          <el-radio-button :label="true">收起</el-radio-button> -->
        </el-radio-group>
        <el-menu default-active="1" class="el-menu-vertical-demo" @open="handleOpen" @close="handleClose" :collapse="isCollapse">
            <el-menu-item index="1">
              <i class="el-icon-s-home" style="margin-right: 10px; font-size: 20px;"></i>
              <span slot="title">管理首页</span>
            </el-menu-item>
            <el-submenu index="2">
              <span slot="title">
                <i class="el-icon-s-custom" style="margin-right: 10px; font-size: 20px;"></i>
                <span>学员管理</span>
              </span>
              <el-menu-item index="2-1">
                <i class="el-icon-s-order" style="margin-right: 10px; font-size: 20px;"></i>
                <span>学员项目管理</span>
              </el-menu-item>
            </el-submenu>
            <el-menu-item index="3">
              <i class="el-icon-chat-dot-round" style="margin-right: 10px; font-size: 20px;"></i>
              <span>个人中心</span>
            </el-menu-item>
        </el-menu>
      </el-aside>
      <el-container>
        <!-- 头部 -->
        <el-header>
          <el-row type="flex" class="row-bg" justify="space-between">
            <el-col :span="6"><div class="grid-content bg-purple"></div></el-col>
            <el-col :span="6"><div class="grid-content bg-purple-light"></div></el-col>
            <el-col :span="6"><div class="grid-content bg-purple"></div></el-col>
          </el-row>
        </el-header>
        <!-- 主体 -->
        <el-main>Main</el-main>
      </el-container>
    </el-container>
  </div>
</template>

<style>
/* 整体 */
  .el-header, .el-footer {
    background-color: #B3C0D1;
    color: #333;
    text-align: center;
    line-height: 60px;
  }
  
  .el-aside {
    background-color: #D3DCE6;
    color: #333;
    text-align: center;
    line-height: 200px;
  }
  
  .el-main {
    background-color: #E9EEF3;
    color: #333;
    text-align: center;
    line-height: 160px;
  }
  
  body > .el-container {
    margin-bottom: 40px;
  }
  
  .el-container:nth-child(5) .el-aside,
  .el-container:nth-child(6) .el-aside {
    line-height: 260px;
  }
  
  .el-container:nth-child(7) .el-aside {
    line-height: 320px;
  }
  /* 导航 */
   .el-menu-vertical-demo:not(.el-menu--collapse) {
    width: 200px;
    min-height: 400px;
  }

  /* 头部 */
  .el-row {
    margin-bottom: 20px;
    &:last-child {
      margin-bottom: 0;
    }
  }
  .el-col {
    border-radius: 4px;
  }
  .bg-purple-dark {
    background: #99a9bf;
  }
  .bg-purple {
    background: #d3dce6;
  }
  .bg-purple-light {
    background: #e5e9f2;
  }
  .grid-content {
    border-radius: 4px;
    min-height: 36px;
  }
  .row-bg {
    padding: 10px 0;
    background-color: #f9fafc;
  }

</style>

<script>
  export default {
    data() {
      return {
        isCollapse: false
      };
    },
    methods: {
      handleOpen(key, keyPath) {
        console.log(key, keyPath);
      },
      handleClose(key, keyPath) {
        console.log(key, keyPath);
      }
    }
  }
</script>