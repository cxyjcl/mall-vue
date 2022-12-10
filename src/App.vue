<template>
  <el-container>
    <el-header>
      <div class="header-left">
        <div class="header-title">淘宝网</div>
        <div class="header-desc">可以搜电饭煲的网站</div>
      </div>
      <div class="header-right">
        <span>注册</span>
        <el-divider direction="vertical"></el-divider>
        <span>登陆</span>
      </div>
    </el-header>


    <el-main>
      <div class="main-search">
        <img class="logo" :src="require('@/assets/taobao_logo.png')" />
        <div class="search">
          <el-input placeholder="请输入内容" v-model="input3" class="input-with-select">
            <el-button slot="append" icon="el-icon-search"></el-button>
          </el-input>
        </div>
      </div>
      <div class="shop-menu">
        <div class="menu">
          <el-menu :default-active="activeIndex" mode="horizontal">
            <el-submenu index="1">
              <template slot="title">女装</template>
              <el-menu-item index="1-1">选项1</el-menu-item>
              <el-menu-item index="1-2">选项2</el-menu-item>
              <el-menu-item index="1-3">选项3</el-menu-item>
              <el-submenu index="1-4">
                <template slot="title">选项4</template>
                <el-menu-item index="1-4-1">选项1</el-menu-item>
                <el-menu-item index="1-4-2">选项2</el-menu-item>
                <el-menu-item index="1-4-3">选项3</el-menu-item>
              </el-submenu>
            </el-submenu>
             <el-submenu index="2">
              <template slot="title">男装</template>
              <el-menu-item index="2-1">选项1</el-menu-item>
              <el-menu-item index="2-2">选项2</el-menu-item>
              <el-menu-item index="2-3">选项3</el-menu-item>
              <el-submenu index="2-4">
                <template slot="title">选项4</template>
                <el-menu-item index="2-4-1">选项1</el-menu-item>
                <el-menu-item index="2-4-2">选项2</el-menu-item>
                <el-menu-item index="2-4-3">选项3</el-menu-item>
              </el-submenu>
            </el-submenu>
            <el-submenu index="3">
              <template slot="title">童装</template>
              <el-menu-item index="3-1">选项1</el-menu-item>
              <el-menu-item index="3-2">选项2</el-menu-item>
              <el-menu-item index="3-3">选项3</el-menu-item>
              <el-submenu index="3-4">
                <template slot="title">选项4</template>
                <el-menu-item index="3-4-1">选项1</el-menu-item>
                <el-menu-item index="3-4-2">选项2</el-menu-item>
                <el-menu-item index="3-4-3">选项3</el-menu-item>
              </el-submenu>
            </el-submenu>
          </el-menu>
        </div>
        <el-carousel :interval="50·00" arrow="always">
          <el-carousel-item v-for="item in 4" :key="item">
            <img :src="require('@/assets/test_picture.png')" />
          </el-carousel-item>
        </el-carousel>
      </div>
    </el-main>


    <el-footer>Footer</el-footer>


  </el-container>

</template>
<style scoped>
.el-header {
  border-bottom: 1px solid transparent;
  box-shadow: 0 3px 5px 0px rgb(64 60 67 / 16%);
  margin-bottom: 20px;
  border-radius: 4px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.el-divider {
  margin-top: 3px;
}

.header-left {
  display: flex;
}

.header-right {
  display: flex;
  justify-content: flex-end;
  margin-right: 12px;
}

.header-desc {
  margin-left: 12px;
}

.el-breadcrumb {
  align-items: center;
}

.logo {
  width: 100px;
  height: 40px;
  margin-left: 32px;
}

.main-search {
  display: flex;
  justify-content: space-between;
  margin-bottom: 20px;
}

.search {
  margin-left: 15px;
}

.shop-menu {
  display: flex;
  justify-content: space-between;

}

.menu {
  width: 400px;
}

.shop-menu img {
  width: 100%;
  height: 300px;
}

.el-menu.el-menu--horizontal{
  border-bottom: 0px;
}
.el-carousel {
  width: 100%;
  height: 400px;
}
</style>

<script>
export default {
  name: 'App'
}
</script>
