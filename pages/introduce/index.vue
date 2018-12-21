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
    <div class="banner-about">
      <div class="container">
        <h1>信任&nbsp;&nbsp;创新&nbsp;&nbsp;实干&nbsp;&nbsp;成功</h1>
      </div>
    </div>
    <div class="aboutUs">
      <div class="container">
        <div class="title">
          <h2>关于华盛</h2>
          <h2>About Us</h2>
        </div>
        <p>
         华盛陶粒是目前陶粒行业集研发、生产、销售、服务于一体的专业化陶粒企业。有着10余条生产线。50多名员工，全规格陶粒年产量达到20万立方。目前办事处设在南京江宁，欢迎各界人士前来参观、考察、洽谈业务，华盛陶粒，专注于保温建材节能领域，坚持“稳健经营、持续创新、开放合作”。华盛陶粒拥有雄厚的技术力量，先进的生产设备，庞大的精英生产团队，为企业和客户提供满意的产品和服务，并致力于节能、减排、环保、创造社会效益，实干赢取未来，创新成就梦想。
        </p>
        <img src="http://www.njhuasheng.cn/images/up_images/201891017423.jpg" alt="">
      </div>
    </div>
    <div class="contactUs">
      <div class="container">
        <div class="title">
          <h2>联系华盛</h2>
          <h2>Contact Us</h2>
        </div>
        <p>
          <label>公司地址：</label>江苏省南京市雨花台区大周路软件谷科创城C1南 <br>
          <label>服务热线：</label>400-184-0001 <br>
          <label>QQ咨询：</label><a target="_blank" href="http://wpa.qq.com/msgrd?v=3&amp;uin=2853573559&amp;site=qq&amp;menu=yes">2853573559</a>
        </p>
      </div>
    </div>
    <div class="jion">
      <div class="container">
        <p>
          我们是一群热血、激情、有个性的奋斗者<br>
          我们是一个从不妥协、坚信实干、追求卓越的团队<br>
          我们期待你的加入<br>
        </p>
        <a href="javascript:;" class="dis-no">诚聘精英</a>
      </div>
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
        activeIndex: '5',
        banner: 'http://www.bm001.com/r/cms/bm001new/default/img/about/banner.jpg',
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

  .banner-about {
    height: 500px;
    background: url(http://www.bm001.com/r/cms/bm001new/default/img/about/banner.jpg) no-repeat center;
  }

  .container {
    text-align: center;
    zoom: 1;
    width: 1200px;
    margin: 0 auto;
    overflow: visible;
    clear: both;
    position: relative;
  }

  .container:before {
    display: table;
    content: " ";
  }

  .container h1 {
    width: 100%;
    margin-top: 160px;
    font-size: 72px;
    font-family: '华文细黑';
    padding-left: 0;
    color: #333;
  }

  .aboutUs {
    height: 568px;
  }

  .container:before {
    display: table;
    content: " ";
  }

  .title {
    margin-top: 80px;
    margin-bottom: 60px;
    position: relative;
  }

  .title h2 {
    width: 640px;
    font-size: 32px;
    font-weight: 700;
    line-height: 45px;
    color: #333;
    text-align: left;
  }

  .title h2:last-child {
    font-weight: 400;
    margin-top: 5px;
  }

  .title:after {
    content: "";
    display: block;
    width: 80px;
    height: 4px;
    background: #4dadf7;
    margin-top: 42px;
  }

  .aboutUs .container p {
    margin-top: 40px;
    width: 356px;
    font-size: 16px;
    color: #999;
    line-height: 24px;
    text-align: justify;
  }

  .aboutUs .container img{
    position: absolute;
    right: 0;
    height: 425px;
    top: 85px;
    width: 624px;
  }
</style>
