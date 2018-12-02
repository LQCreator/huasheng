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
    <div class="company">
      <div class="container swiper-container-sy">
        <div class="company-left">
          <div class="title">
            <h2>关于我们</h2>
            <h2>About Us</h2>
          </div>
          <div class="company-content">
            <div class="company-info">
              华盛陶粒是目前陶粒行业集研发、生产、销售、服务于一体的专业化陶粒企业。有着10余条生产线。50多名员工，全规格陶粒年产量达到20万立方。目前办事处设在南京江宁，欢迎各界人士前来参观、考察、洽谈业务，华盛陶粒，专注于保温建材节能领域，坚持“稳健经营、持续创新、开放合作”。华盛陶粒拥有雄厚的技术力量，先进的生产设备，庞大的精英生产团队，为企业和客户提供满意的产品和服务，并致力于节能、减排、环保、创造社会效益，实干赢取未来，创新成就梦想
            </div>
            <a class="company-more" href="">了解更多</a>
            <img :src="companyHonor" alt="">
            <div class="honor-contain">
              <ul :style="{ left: honorLeft + 'px' }">
                <li v-for="(honorImg,index) in honorList" :key="index">
                  <a href="">
                    <img class="honor-img" :src="honorImg.url">
                  </a>
                </li>
              </ul>
            </div>
          </div>
        </div>
        <div class="company-right">
          <img class="company-img" :src="companyIntroduce">
        </div>
      </div>
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
            <a href="">
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
        caseList: [
          {
            url: 'http://www.njhuasheng.cn/images/up_images/2018914134214.jpg',
            name: '恒大建筑合作案例'
          },
          {
            url: 'http://www.njhuasheng.cn/images/up_images/2018914133727.jpg',
            name: '鑫科建筑合作案例'
          },
          {
            url: 'http://www.njhuasheng.cn/images/up_images/201891413359.jpg',
            name: '施工现场产品验收'
          },
          {
            url: 'http://www.njhuasheng.cn/images/up_images/2018914133413.jpg',
            name: '鲁南酒店合作案例'
          },
          {
            url: 'http://www.njhuasheng.cn/images/up_images/2018914134327.jpg',
            name: '水电四局合作案例'
          },
          {
            url: 'http://www.njhuasheng.cn/images/up_images/201891413100.jpg',
            name: '中建集团合作案例'
          },
        ],
        companyIntroduce: 'http://www.shjztl.com/web/uploads/cover/20180703/jXM0VR9FG90t5HrZ3J705OWy32x8t313.jpg',
        companyHonor: 'http://www.shjztl.com/web/template/pctpl/images/i02.png',
        honorList: [
          {
            url: 'http://www.shjztl.com/web/uploads/cover/20180705/j3v9305ka28BmKj38Q0Huhr870vg2w1h.jpg'
          },
          {
            url: 'http://www.shjztl.com/web/uploads/cover/20180705/j0151kWS71IHbU1g27033Tk2kranL31u.jpg'
          },
          {
            url: 'http://www.shjztl.com/web/uploads/cover/20180705/j3w7p85RjK5k3u5flZ005axPG570E0r1.jpg'
          },
          {
            url: 'http://www.shjztl.com/web/uploads/cover/20180705/j3v9305ka28BmKj38Q0Huhr870vg2w1h.jpg'
          },
          {
            url: 'http://www.shjztl.com/web/uploads/cover/20180705/j0151kWS71IHbU1g27033Tk2kranL31u.jpg'
          },
          {
            url: 'http://www.shjztl.com/web/uploads/cover/20180705/j3w7p85RjK5k3u5flZ005axPG570E0r1.jpg'
          },
        ],
        honorLeft: 0
      }
    },
    mounted() {
      setInterval(this._changeHonorLeft, 10);
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
      _changeHonorLeft(){
        if (this.honorLeft < -710) {
          this.honorLeft = 0
        } else {

          this.honorLeft -= 1;
        }

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

  .company {
    height: 654px;
    background-image: url("http://www.shjztl.com/web/template/pctpl/images/01.jpg");
  }

  .product {
    height: 594px;
  }

  .company-left {
    float: left;
    width: 750px;
    height: 654px;
  }

  .company-right {
    float: right;
    width: 450px;
    height: 654px;
    position: relative;
  }

  .company-img {
    position: absolute;
    width: 450px;
    height: 450px;
    bottom: 0;
    right: 0;
  }

  .company-content {
    width: 700px;
  }

  .company-info {
    text-indent: 2em;
    line-height: 26px;
    color: #666;
  }

  .company-more {
    display: inline-block;
    float: right;
    clear: both;
    width: 120px;
    height: 34px;
    background-color: #0057ba;
    border-radius: 7px;
    text-align: center;
    line-height: 32px;
    color: #fff;
    margin-top: 12px;
  }

  .company-content img {
    display: block;
    clear: both;
  }

  .honor-contain {
    width: 714px;
    height: 140px;
    position: relative;
    margin-top: 20px;
    overflow: hidden;
  }

  .honor-contain ul {
    position: absolute;
    left: 0;
    top: 0;
    overflow: hidden;
    width: 1500px;
    /*width: 724px;*/
  }

  .honor-contain ul li {
    float: left;
    width: 218px;
    height: 140px;
    list-style: none;
    margin-right: 20px;
  }

  .honor-contain ul li:last-child {
    margin-right: 0;
  }

  .honor-img {
    width: 100%;
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
    height: 248px;
    margin-right: 106px;
    border: 1px solid #f5f5f5;
    box-shadow: 3.24px 2.35px 10px 0 rgba(0, 0, 0, .1);
    text-align: center !important;
  }

  .product .container ul li a {
    display: block;
    width: 220px;
    height: 200px;
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
    height: 200px;
  }

  .case {
    height: 908px;
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

  .case-img {
    width: 100%;
    height: 175px;
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
</style>
