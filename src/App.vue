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
          <el-input placeholder="请输入内容" class="input-with-select">
            <el-button slot="append" icon="el-icon-search"></el-button>
          </el-input>
        </div>
      </div>
      <div class="shop-menu">
        <div class="menu">
          <el-menu mode="horizontal">
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
        <el-carousel :interval="5000" arrow="always">
          <el-carousel-item v-for="item in 4" :key="item">
            <img :src="require('@/assets/test_picture.png')" />
          </el-carousel-item>
        </el-carousel>
      </div>
      <div class="recommend">
        <span class="recommend-header">猜你喜欢</span>
        <div v-infinite-scroll="load" infinite-scroll-disabled="disabled">
          <div v-for="i in count" class="list-item">
            <div class="item">
              <img :src="require('@/assets/default_recommend_picture.jpg')" />
              <div class="content">
                <div id="title">冬天床上牛奶绒四件套双面绒法兰珊瑚绒加厚被套床单冬季加绒三4</div>
                <div id="tag-item">送运费险</div>
                <div id="price">¥ 139</div>
              </div>
            </div>
            <div class="item">
              <img :src="require('@/assets/default_recommend_picture.jpg')" />
              <div class="content">
                <div id="title">冬天床上牛奶绒四件套双面绒法兰珊瑚绒加厚被套床单冬季加绒三4</div>
                <div id="tag-item">送运费险</div>
                <div id="price">¥ 139</div>
              </div>
            </div>
          </div>
        </div>
        <p v-if="loading">加载中...</p>
        <p v-if="noMore" class="noMore">没有更多了</p>
      </div>
    </el-main>


    <el-footer>
      <div class="footer-copyright"> Copyright 2004 - 2022</div>
    </el-footer>


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
  background-color: #f5f5f5;
}

.el-main {
  background-color: #f5f5f5;
  margin: 20px;
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

.el-menu.el-menu--horizontal {
  border-bottom: 0px;
}

.el-carousel {
  width: 100%;
  height: 300px;
}

.recommend-header {
  color: #111;
  font-weight: bold;
  font-size: 24px;
  line-height: 24px;
  display: flex;
  justify-content: flex-start;
  margin-left: 20px;
}

.recommend {
  padding-top: 20px;
}

.list-item {
  display: flex;
  justify-content: space-between;
}

.item {
  display: flex;
  width: 440px;
  height: 174px;
  margin: 20px 20px 20px 0px;
  padding-top: 20px;
  padding-right: 20px;
  padding-left: 20px;
  overflow: hidden;
  color: #333;
  background-color: #f7f9fa;
  border: 1px solid #f7f9fa;
}

.item img {
  width: 150px;
  height: 150px;
}

.item #title {
  max-height: 46px;
  margin: 6px 0 2px 0;
  overflow: hidden;
  color: #333;
  font-size: 16px;
  line-height: 23px;
  display: inline-block;
}

.item #tag-item {
  height: 20px;
  margin-right: 6px;
  padding: 0 4px;
  color: #ff5000;
  font-size: 12px;
  line-height: 18px;
  vertical-align: top;
  border: 1px solid #ff5000;
  -webkit-border-radius: 3px;
  -moz-border-radius: 3px;
  border-radius: 3px;
  display: inline-block;
}

.item .content {
  margin-left: 12px;
}

.item #price {
  margin-top: 50px;
}

.noMore{
  text-align: center;
}

.footer-copyright {
  line-height: 20px;
  text-align: center;
  width: 960px;
  margin: 0 auto;
}
</style>

<script>
export default {
  name: 'App',
  data() {
    return {
      count: 5,
      loading: false
    }
  },
  computed: {
    noMore() {
      return this.count >= 5
    },
    disabled() {
      return this.loading || this.noMore
    }
  },
  methods: {
    load() {
      this.loading = true
      setTimeout(() => {
        this.count += 2
        this.loading = false
      }, 2000)
    }
  }
}
</script>
