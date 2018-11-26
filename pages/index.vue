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
    <div class="block">
      <el-carousel trigger="click" height="500px">
        <el-carousel-item v-for="(img,index) in bannerList" :key="index">
          <img class="banner-img" :src="img.url">
        </el-carousel-item>
      </el-carousel>
    </div>
    <div class="product">
      <div class="container swiper-container-sy">
        <div class="title">
          <p>南京华盛新型节能环保材料有限公司本着“服务与客户至上，打造地区陶粒实惠价”。热诚欢迎各界朋友前来参观、考察、洽谈业务。</p>
          <h2>产品中心</h2>
          <h2>Product Center</h2>
        </div>
        <ul class="swiper-wrapper">
          <li class="swiper-slide" v-for="(product,index) in productList" :key="index">
            <a href="//bm001.com/product/ywd/">
              <img class="product-img" :src="product.url">
              <h3>{{product.name}}</h3>
            </a>
          </li>
        </ul>
        <div class="swiper-pagination"></div>
      </div>
    </div>
    <div class="case">
      <div class="container swiper-container-sy">
        <div class="title">
          <p>南京华盛新型节能环保材料有限公司本着“服务与客户至上，打造地区陶粒实惠价”。热诚欢迎各界朋友前来参观、考察、洽谈业务。</p>
          <h2>工程案例</h2>
          <h2>Engineering Case</h2>
        </div>
        <ul>
          <li v-for="(engCase,index) in caseList" :key="index">
            <img class="case-img" :src="engCase.url">
            <p>{{engCase.name}}</p>
          </li>
        </ul>
        <div class="swiper-pagination"></div>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        activeIndex: '1',
        bannerList: [
          {url: 'http://www.njhuasheng.cn/images/up_images/201891413444.jpg'},
          {url: 'http://www.njhuasheng.cn/images/up_images/20189521445.jpg'},
          {url: 'http://www.njhuasheng.cn/images/up_images/201891413142.jpg'},
        ],
        productList: [
          {
            name: '陶粒',
            url: 'http://www.njhuasheng.cn/images/up_images/2018952250.jpg',
          },
          {
            name: '岩棉板',
            url: 'http://www.njhuasheng.cn/images/up_images/201895221612.jpg',
          },
          {
            name: '挤塑板',
            url: 'http://www.njhuasheng.cn/images/up_images/20189522197.jpg',
          },
          {
            name: '陶粒加气块',
            url: 'http://www.njhuasheng.cn/images/up_images/201895222211.jpg',
          },
        ],
        caseList:[
          {
            url: 'http://www.njhuasheng.cn/images/up_images/2018914134214.jpg',
            name:'恒大建筑合作案例'
          },
          {
            url: 'http://www.njhuasheng.cn/images/up_images/2018914133727.jpg',
            name:'鑫科建筑合作案例'
          },
          {
            url: 'http://www.njhuasheng.cn/images/up_images/201891413359.jpg',
            name:'施工现场产品验收'
          },
          {
            url: 'http://www.njhuasheng.cn/images/up_images/2018914133413.jpg',
            name:'鲁南酒店合作案例'
          },
          {
            url: 'http://www.njhuasheng.cn/images/up_images/2018914134327.jpg',
            name:'水电四局合作案例'
          },
          {
            url: 'http://www.njhuasheng.cn/images/up_images/201891413100.jpg',
            name:'中建集团合作案例'
          },





        ]
      }
    },
    methods: {
      handleSelect(key, keyPath) {
        console.log(key, keyPath)
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

  .banner-img {
    width: 100%;
    height: 100%;
  }

  .product {
    height: 594px;
  }

  .container {
    zoom: 1;
    width: 1200px;
    margin: 0 auto;
    overflow: visible;
    clear: both;
  }

  .container:before {
    display: table;
    content: " ";
  }

  .title {
    margin-top: 80px;
    margin-bottom: 60px;
  }

  .title p {
    text-align: left;
    margin-top: 0;
    width: 520px;
    float: right;
    line-height: 26px;
    color: #999999;
    font-size: 16px;
  }

  .title h2 {
    width: 640px;
    font-size: 32px;
    font-weight: 700;
    line-height: 45px;
    color: #333;
  }

  .title:after {
    content: "";
    display: block;
    width: 80px;
    height: 4px;
    background: #4dadf7;
    margin-top: 42px;
  }

  .product .container ul {
    clear: both;
    zoom: 1;
    overflow: visible;
  }

  .product .container ul li {
    float: left;
    width: 220px;
    height: 268px;
    margin-right: 106px;
    border: 1px solid #f5f5f5;
    box-shadow: 3.24px 2.35px 10px 0 rgba(0, 0, 0, .1);
    text-align: center !important;
  }

  .product .container ul li a {
    display: block;
    width: 220px;
    height: 220px;
  }

  .product .container ul li h3 {
    color: #333;
    font-size: 18px;
    font-weight: 700;
    margin: 12px 0;
  }

  .product .container ul li:last-child {
    margin-right: 0;
  }

  .product .container ul:after {
    content: " ";
    display: block;
    height: 0;
    clear: both;
    visibility: hidden;
  }

  .product-img {
    width: 100%;
    height: 220px;
  }

  .case {
    height: 782px;
    background: #f7f7f7;
  }

  .case ul {
    clear: both;
    zoom: 1;
    overflow: hidden;
  }

  .case ul li:nth-child(1), .case ul li:nth-child(2), .case ul li:nth-child(3) {
    border-bottom: 1px solid #d2d2d2;
    border-right: 1px solid #d2d2d2;
  }

  .case ul li:nth-child(4), .case ul li:nth-child(5) {
    border-right: 1px solid #d2d2d2;
  }

  .case ul li:nth-child(3) {
    border-right: 0;
  }

  .case ul li {
    float: left;
    width: 400px;
    height: 260px;
    padding: 36px 68px;
    text-align: center;
  }

  .case-img{
    width: 100%;
    height: 175px;
  }
</style>
