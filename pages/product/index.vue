<template>
  <div>
    <el-menu
      :default-active="activeIndex"
      class="el-menu"
      mode="horizontal"
      background-color="#545c64"
      text-color="#fff"
      active-text-color="#ffd04b"
      @select="handleSelect">
      <el-menu-item index="1">首页</el-menu-item>
      <el-menu-item index="2">产品中心</el-menu-item>
      <el-menu-item index="3">新闻资讯</el-menu-item>
      <el-menu-item index="4">工程案例</el-menu-item>
      <el-menu-item index="5">公司简介</el-menu-item>
      <el-menu-item index="6">联系我们</el-menu-item>
    </el-menu>
    <div class="companyIcon">
      <img
        src="~/assets/company.jpg"
        alt="公司名称">
    </div>
    <div class="product-banner">
      <img :src="banner" alt="">
    </div>
    <div class=product-main>
      <div class="product-nav">
        <div>
          <el-breadcrumb separator-class="el-icon-arrow-right">
            <el-breadcrumb-item v-for="(nav,index) in navList" :to="{ path: nav.url }">{{nav.name}}</el-breadcrumb-item>
          </el-breadcrumb>
        </div>
      </div>
      <el-row class="menu-contain">
        <el-col :span="5" class="menu-left">
          <h2>产品中心</h2>
          <el-menu
            default-active="2"
            class="el-menu-vertical-demo"
            @open="handleOpen"
            @close="handleClose">
            <el-menu-item index="1">
              <i class="el-icon-menu"></i>
              <span slot="title">陶粒</span>
            </el-menu-item>
            <el-menu-item index="2">
              <i class="el-icon-menu"></i>
              <span slot="title">岩棉板</span>
            </el-menu-item>
            <el-menu-item index="3">
              <i class="el-icon-menu"></i>
              <span slot="title">挤塑板</span>
            </el-menu-item>
            <el-menu-item index="4">
              <i class="el-icon-menu"></i>
              <span slot="title">陶粒加气块</span>
            </el-menu-item>
          </el-menu>
        </el-col>
        <el-col :offset="1" :span="18">
          <el-row gutter="10">
            <el-col :span="8">1</el-col>
            <el-col :span="8">2</el-col>
            <el-col :span="8">3</el-col>
          </el-row>
          <el-row gutter="10">
            <el-col :span="8">4</el-col>
            <el-col :span="8">5</el-col>
            <el-col :span="8">6</el-col>
          </el-row>

        </el-col>
      </el-row>
    </div>

    <div class="footer">
      <div class="footer-container">
        <div class="footer-left">
          <div class="foot-title">
            <h6>联系我们</h6>
            <p>Contacts</p>
          </div>
          <div class="foot-cont">
            <p>南京华盛新型节能环保材料有限公司 </p>
            <p>咨询电话：15380861888</p>
            <p>地址：南京市江宁区秣陵街道天元东路228号财富广场莱茵大厦1404室(高新园) </p>
          </div>
        </div>
        <div class="footer-right">
          <img src="http://pic.qianmi.com/elife/bmweb/qrcode-bm-2.jpg" alt="">
          <p>扫码关注南京华盛公众号</p>
          <p>查看更多信息</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        activeIndex: '2',
        banner: 'http://www.shjztl.com/web/uploads/cover/20180703/j1z1mZ7XMr1aPU0e3J5k8leb5103X585.jpg',
        navList: [
          {name: '首页', url: '/'},
          {name: '产品中心', url: '/product'},
        ]
      }
    },
    methods: {
      handleSelect(key, keyPath) {
        if (key === "1") {
          this.$router.push({
            path: '/'
          });
        } else if (key === "2") {
          this.$router.push({
            path: '/product'
          });
        } else if (key === "3") {
          this.$router.push({
            path: '/news'
          });
        } else if (key === "4") {
          this.$router.push({
            path: '/case'
          });
        } else if (key === "5") {
          this.$router.push({
            path: '/introduce'
          });
        } else if (key === "6") {
          this.$router.push({
            path: '/contact'
          });
        }
      },
      handleOpen(key, keyPath) {
        console.log(key, keyPath);
      },
      handleClose(key, keyPath) {
        console.log(key, keyPath);
      }
    }
  }
</script>

<style>
  .el-menu {
    padding-left: 60%;
  }

  .companyIcon {
    width: 30%;
    height: 60px;
    position: absolute;
    left: 0;
    top: 0;
  }

  .companyIcon img {
    width: 100%;
    height: 100%;
  }

  .el-carousel-item h3 {
    color: #475669;
    font-size: 14px;
    opacity: 0.75;
    line-height: 150px;
    margin: 0;
  }

  .footer {
    box-sizing: border-box;
    padding: 50px 0;
    min-height: 300px;
    background-color: #000;
  }

  .footer-container {
    zoom: 1;
    width: 1200px;
    margin: 0 auto;
    overflow: visible;
    clear: both;
    position: relative;
  }

  .foot-title {
    padding-bottom: 30px;
  }

  .foot-title:after {
    content: "";
    display: block;
    width: 18px;
    height: 2px;
    background-color: #666;
    position: relative;
    top: 20px;
  }

  .foot-title h6 {
    font-size: 16px;
    line-height: 36px;
    letter-spacing: 1px;
    color: #f6f7f8;
  }

  .foot-title p {
    font-size: 12px;
    line-height: 1;
    color: #666;
  }

  .foot-cont p {
    display: block;
    font-size: 14px;
    line-height: 30px;
    letter-spacing: 1px;
    color: #666;
  }

  .footer-right {
    position: absolute;
    top: 0;
    right: 0;
    width: 200px;
  }

  .footer-right img {
    display: block;
    margin: 0 auto 10px;
    width: 150px;
    height: 150px;
  }

  .footer-right p {
    display: block;
    margin: 0 auto;
    font-size: 14px;
    line-height: 20px;
    letter-spacing: 1px;
    color: #666;
    text-align: center;
  }

  .product-banner {
    width: 100%;
    height: 450px;
  }

  .product-banner img {
    width: 100%;
    height: 450px;
  }

  .product-main {
    padding: 20px 30px;
    box-sizing: border-box;
    margin: 0 auto;
    position: relative;
    box-shadow: 0 0 15px rgba(0, 0, 0, 0.2);
    background: #fff;
    width: 1200px;
  }

  .product-nav {
    height: 42px;
    background-image: url("http://www.shjztl.com/web/template/pctpl/images/09.jpg");
    background-repeat: no-repeat;
    background-position: left top;
    background-color: #f9f8f8;
    padding-left: 6em;
    margin-bottom: 28px;
  }

  .product-nav div {
    line-height: 42px;
    height: 42px;
  }

  .product-main .el-menu {
    padding-left: 0;
  }

  .menu-left h2{
    width: 100%;
    height: 70px;
    line-height: 68px;
    background-color: #05C;
    color: #fff;
    font-size: 30px;
    font-weight: 400;
    text-align: center;
  }

</style>
