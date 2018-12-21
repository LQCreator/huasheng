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
            default-active=""
            class="el-menu-case"
            @open="handleOpen"
            @close="handleClose"
            @select="selectCase">
            <el-menu-item index="1">
              <span slot="title">恒大建筑</span>
            </el-menu-item>
            <el-menu-item index="2">
              <span slot="title">鑫科建筑</span>
            </el-menu-item>
            <el-menu-item index="3">
              <span slot="title">鲁南酒店</span>
            </el-menu-item>
            <el-menu-item index="4">
              <span slot="title">水电四局</span>
            </el-menu-item>
            <el-menu-item index="5">
              <span slot="title">中建集团</span>
            </el-menu-item>
          </el-menu>
          <h2>新闻资讯</h2>
          <el-menu
            default-active=""
            class="news"
            @open="handleOpen"
            @close="handleClose"
            @select="selectNews">
            <el-menu-item index="1">
              <i class="el-icon-document"></i>
              <span slot="title">陶粒简析陶粒在生活中的巧用</span>
            </el-menu-item>
            <el-menu-item index="2">
              <i class="el-icon-document"></i>
              <span slot="title">南京华盛推出陶粒加气砌块</span>
            </el-menu-item>
            <el-menu-item index="3">
              <i class="el-icon-document"></i>
              <span slot="title">南京华盛陶粒成为环保节能陶粒</span>
            </el-menu-item>
            <el-menu-item index="4">
              <i class="el-icon-document"></i>
              <span slot="title">华盛陶粒厂粘土陶粒使用“土法</span>
            </el-menu-item>
            <el-menu-item index="5">
              <i class="el-icon-document"></i>
              <span slot="title">陶粒的构成特点及功能？</span>
            </el-menu-item>
          </el-menu>
        </el-col>
        <ul class="product-list" v-if="!caseDetail">
          <li class="product-item" v-for="(caseItem,index) in caseList" :key="index">
            <a>
              <img class="product-item-img" :src="caseItem.url">
              <p class="product-name">{{caseItem.name}}</p>
            </a>
          </li>
        </ul>:
        <div  v-html="content" v-if="caseDetail"></div>
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
      return{
        activeIndex: '4',
        banner: 'http://www.shjztl.com/web/uploads/cover/20180703/j1z1mZ7XMr1aPU0e3J5k8leb5103X585.jpg',
        navList: [
          {name: '首页', url: '/'},
          {name: '工程案例', url: '/news'}
        ],
        caseList: [
          {
            id: 1,
            name: '恒大建筑合作案例',
            url: 'http://www.njhuasheng.cn/images/up_images/2018914134214.jpg'
          },{
            id: 2,
            name: '鑫科建筑合作案例',
            url: 'http://www.njhuasheng.cn/images/up_images/2018914133727.jpg'
          },{
            id: 3,
            name: '鲁南酒店合作案例',
            url: 'http://www.njhuasheng.cn/images/up_images/2018914133413.jpg'
          },{
            id: 4,
            name: '水电四局合作案例',
            url: 'http://www.njhuasheng.cn/images/up_images/2018914134327.jpg'
          },{
            id: 5,
            name: '中建集团合作案例',
            url: 'http://www.njhuasheng.cn/images/up_images/201891413100.jpg'
          }],
        caseDetail: false,
        content: '<div class="article">' +
        '<h3 class="articleTit">恒大建筑合作案例</h3>' +
        '<div class="articleCon">' +
        '<img src="http://www.njhuasheng.cn/images/up_images/2018914134214.jpg" width="600" height="400" style="width: 600px; height: 400px;">' +
        '</div>' +
        '<h3 class="tag">相关标签：</h3>' +
        '<div class="page">上一篇：无<br>下一篇：<a href="javascript:void(0)">鑫科建筑合作案例</a></div>'+
        '</div>',
        caseDetailList: [{
          id: 1,
          content: '<div class="article">' +
          '<h3 class="articleTit">鑫科建筑合作案例</h3>' +
          '<div class="articleCon">' +
          '<img src="http://www.njhuasheng.cn/images/up_images/2018914133727.jpg" width="600" height="400" style="width: 600px; height: 400px;">' +
          '</div>' +
          '<h3 class="tag">相关标签：</h3>' +
          '<div class="page">上一篇：恒大建筑合作案例<br>下一篇：<a href="javascript:void(0)">中建集团合作案例</a></div>'+
          '</div>'
        }, {
          id: 2,
          content: '<div class="article">' +
          '<h3 class="articleTit">中建集团合作案例</h3>' +
          '<div class="articleCon">' +
          '<img src="http://www.njhuasheng.cn/images/up_images/201891413100.jpg" width="600" height="400" style="width: 600px; height: 400px;">' +
          '</div>' +
          '<h3 class="tag">相关标签：</h3>' +
          '<div class="page">上一篇：鑫科建筑合作案例<br>下一篇：<a href="javascript:void(0)">水电四局合作案例</a></div>'+
          '</div>'
        },
          {
            id: 3,
            content:'<div class="article">' +
            '<h3 class="articleTit">水电四局合作案例</h3>' +
            '<div class="articleCon">' +
            '<img src="http://www.njhuasheng.cn/images/up_images/2018914134214.jpg" width="600" height="400" style="width: 600px; height: 400px;">' +
            '</div>' +
            '<h3 class="tag">相关标签：</h3>' +
            '<div class="page">上一篇：鲁南酒店合作案例<br>下一篇：<a href="javascript:void(0)">无</a></div>'+
            '</div>'
          },
          {
            id: 4,
            content: '<div class="article">' +
            '<h3 class="articleTit">恒大建筑合作案例</h3>' +
            '<div class="articleCon">' +
            '<img src="http://www.njhuasheng.cn/images/up_images/2018914134214.jpg" width="600" height="400" style="width: 600px; height: 400px;">' +
            '</div>' +
            '<h3 class="tag">相关标签：</h3>' +
            '<div class="page">上一篇：无<br>下一篇：<a href="/resolve/jiangsu55.html">鑫科建筑合作案例</a></div>'+
            '</div>'
          },
          {
            id: 5,
            content: '<div class="article">' +
            '<h3 class="articleTit">恒大建筑合作案例</h3>' +
            '<div class="articleCon">' +
            '<img src="http://www.njhuasheng.cn/images/up_images/2018914134214.jpg" width="600" height="400" style="width: 600px; height: 400px;">' +
            '</div>' +
            '<h3 class="tag">相关标签：</h3>' +
            '<div class="page">上一篇：无<br>下一篇：<a href="/resolve/jiangsu55.html">鑫科建筑合作案例</a></div>'+
            '</div>'
          }]
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
      },
      selectCase(key, keyPath){
        this.caseDetail = true;
        for (let i = 0; i < this.caseDetailList.length; i++) {
          if (key == this.caseDetailList[i].id) {
            this.content = this.caseDetailList[i].content;
          }
        }
      },
      selectNews(key, keyPath){
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

  .product-item-img {
    width: 274px;
    height: 205px;
  }

  .product-list {
    float: left;
    width: 78%;
    margin-left: 12px;
  }

  .product-item {
    float: left;
    margin: 0 10px 10px 10px;
  }

  .product-name {
    text-align: center;
  }

  .el-menu-case .el-menu-item{
    text-align: center;
  }

  .menu-left h2 {
    width: 100%;
    height: 70px;
    line-height: 68px;
    background-color: #05C;
    color: #fff;
    font-size: 30px;
    font-weight: 400;
    text-align: center;
  }

  .news li{
    padding: 0 !important;
  }

  .articleTit {
    font-size: 22px;
    color: #434343;
    text-align: center;
    height: 38px;
    font-weight: 400;
    line-height: 24px;
  }

  .articleCon {
    line-height: 2em;
    color: #666;
    text-align: center;
  }

  h3.tag {
    line-height: 24px;
    border-top: 1px dashed #e0e1dc;
    margin: 10px 10px 0 40px;
    color: #999;
    font-weight: normal;
    padding-top: 8px;
    font-size: 14px;
  }

  .page {
    line-height: 26px;
    border-top: 1px dashed #e0e1dc;
    margin: 6px 10px 0 40px;
    padding-top: 15px;
    font-size: 12px;
    padding-bottom: 25px;
  }

  .product-main .el-menu {
    padding-left: 0;
  }

  .product-nav div {
    line-height: 42px;
    height: 42px;
  }

  .article {
    float: left;
    width: 78%;
    margin-left: 12px;
  }
</style>
