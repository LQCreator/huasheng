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
          <h2>新闻资讯</h2>
          <el-menu
            :default-active="newsIndex"
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
          <h2>产品中心</h2>
          <el-menu
            :default-active="productIndex"
            class="el-menu-vertical-demo"
            @open="handleOpen"
            @close="handleClose"
            @select="selectProduct">
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
        <div v-html="content"></div>
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
    created(){
      let newsIndex = this.$route.params.newsIndex;
      this.newsIndex = newsIndex;
      for (let i = 0; i < this.articleList.length; i++) {
        if (newsIndex == this.articleList[i].type) {
          this.content = this.articleList[i].content;
        }
      }
    },
    data() {
      return {
        activeIndex: '3',
        productIndex: '',
        newsIndex:'1',
        banner: 'http://www.shjztl.com/web/uploads/cover/20180703/j1z1mZ7XMr1aPU0e3J5k8leb5103X585.jpg',
        navList: [
          {name: '首页', url: '/'},
          {name: '新闻资讯', url: '/news'},
        ],
        content: '<div class="article">' +
        '<h3 class="articleTit">陶粒简析陶粒在生活中的巧用？</h3>' +
        '<div class="sub_info line">' +
        '<span>发布日期：2018-12-19 14:49</span> ' +
        '<span>点击量：788</span>' +
        '</div>' +
        '<div class="articleCon">' +
        '<p>陶粒我们都不陌生，通常来讲陶粒是陶质的颗粒总称，它的使用遍及生活的很多方面，今天带大家了解的就是其在水培植物中的作用，一起看看陶粒在生活中的巧用。</p>' +
        '<p>用陶粒来水培植物，能够很快的诱根，而且它的透气作用相当不错，养分也很足，不只简便还很好用。</p>' +
        '<p>尤其是那些根系现已呈现腐朽的植物，假设用陶粒进行诱根的话，作用是很不错的，首要咱们能够先把烂掉的根系部分给切除了，然后用蜡封住切口，放在陶粒中进行固定，还要把水位控制在封蜡的下部，这样一来白根很快就会长出来了。</p>' +
        '<p>如今的许多水培植物大多数是种在室内的，假设运用陶粒去做这些水培植物的培养基的话，它们的透气和湿度方面也就能够得到很好地确保。本来咱们人都不知道，陶粒营养成分是很丰厚的，这样一来在水培植物的进程中就不用为了施肥疑问而忧虑了。而且还具有很高的漂亮作用，咱们都知道许多水培植物都是养在一些质脆的瓶瓶罐罐中的，通常不能够去重压它们，假设你用雨花石或是鹅卵石的话那么也就会呈现过重的情况，很显然这时陶粒就是你的不二之选啦。</p>' +
        '</div>' +
        '</div>',
        articleList: [{
          type: 1,
          content: '<div class="article">' +
          '<h3 class="articleTit">陶粒简析陶粒在生活中的巧用？</h3>' +
          '<div class="sub_info line">' +
          '<span>发布日期：2018-12-19 14:49</span> ' +
          '<span>点击量：788</span>' +
          '</div>' +
          '<div class="articleCon">' +
          '<p>陶粒我们都不陌生，通常来讲陶粒是陶质的颗粒总称，它的使用遍及生活的很多方面，今天带大家了解的就是其在水培植物中的作用，一起看看陶粒在生活中的巧用。</p>' +
          '<p>用陶粒来水培植物，能够很快的诱根，而且它的透气作用相当不错，养分也很足，不只简便还很好用。</p>' +
          '<p>尤其是那些根系现已呈现腐朽的植物，假设用陶粒进行诱根的话，作用是很不错的，首要咱们能够先把烂掉的根系部分给切除了，然后用蜡封住切口，放在陶粒中进行固定，还要把水位控制在封蜡的下部，这样一来白根很快就会长出来了。</p>' +
          '<p>如今的许多水培植物大多数是种在室内的，假设运用陶粒去做这些水培植物的培养基的话，它们的透气和湿度方面也就能够得到很好地确保。本来咱们人都不知道，陶粒营养成分是很丰厚的，这样一来在水培植物的进程中就不用为了施肥疑问而忧虑了。而且还具有很高的漂亮作用，咱们都知道许多水培植物都是养在一些质脆的瓶瓶罐罐中的，通常不能够去重压它们，假设你用雨花石或是鹅卵石的话那么也就会呈现过重的情况，很显然这时陶粒就是你的不二之选啦。</p>' +
          '</div>' +
          '</div>'
        }, {
          type: 2,
          content: '<div class="article">' +
          '<h3 class="articleTit">南京华盛推出可循环使用陶粒加气砌块</h3>' +
          '<div class="sub_info line">' +
          '<span>发布日期：2018-12-19 14:49</span> ' +
          '<span>点击量：544</span>' +
          '</div>' +
          '<div class="articleCon">' +
          '<p>在建筑领域中，墙体保温材料的出现时间不长，但却受到人们的很大重视，尤其是陶粒厂生产的陶粒加气砌块，其中主要的原因之一就是砌块可以循环使用。</p>' +
          '<p>对墙体进行保温是很多建筑工程中都需要完成的，且发展趋势良好，因此很多保温建筑材料不断涌现，其中就包括陶粒厂生产的陶粒加气砌块，它在工业化生产中得以广泛利用。在建筑物的拆除过程中，我们发现大量陶粒加气砌块的废弃物，且这些砌块本身在生产过程中也产生了大量的边角料和废料。</p>' +
          '<p>这些废弃物和废料不仅造成资源的浪费，更严重污染周围的环境，人工清理不仅耽误施工时间，还占用劳动力资源。这是传统“大量生产、大量浪费、大量废弃”的发展模式，完全不符合可持续发展战略。为此，陶粒厂经过多方调研，制定设计出一整套废料综合处理利用的系统，将这些废料进行收集、处理和回收，最后再次作为生产陶粒加气砌块的原料予以使用，从而实现可循环利用的目标。</p>' +
          '</div>' +
          '</div>'
        },
          {
            type: 3,
            content: '<div class="article">' +
            '<h3 class="articleTit">南京华盛陶粒成为环保节能陶粒新选择</h3>' +
            '<div class="sub_info line">' +
            '<span>发布日期：2018-12-19 14:49</span> ' +
            '<span>点击量：544</span>' +
            '</div>' +
            '<div class="articleCon">' +
            '<p>说到陶粒，很多朋友大概都会感到比较陌生，但说到多肉植物种植时使用的辅助料，相信大家就有点印象了。陶粒是陶粒厂生产的产品，也是环保节能新选择。</p>' +
            '<p>陶粒的制作原料多种多样，包括铝矾土、黏土、页岩、城市垃圾、煤矸石、粉煤灰等，其中，城市垃圾和煤矸石制作的陶粒应用范围极广，而且还顺便解决了城市中出现的垃圾污染问题，不仅保护了环境，还节约了对其它能源的消耗，因而陶粒厂推出的垃圾陶粒和煤矸石陶粒受到人们的强烈欢迎。</p>' +
            '<p>在资源严重匮乏的今天，环境污染问题始终是横亘在人们心头的重大难题。现在，陶粒厂生产出多种材质的陶粒，不仅能用来种植植物，还可以制作建筑材料，更能用于污水处理，用途广泛，效果良好。所以说，这些陶粒都是环保节能的新选择。</p>' +
            '</div>' +
            '</div>'
          },
          {
            type: 4,
            content: '<div class="article">' +
            '<h3 class="articleTit">华盛陶粒厂粘土陶粒使用“土法工艺”法生产</h3>' +
            '<div class="sub_info line">' +
            '<span>发布日期：2018-12-19 14:49</span> ' +
            '<span>点击量：544</span>' +
            '</div>' +
            '<div class="articleCon">' +
            '<p>50年代中期我国粘土陶粒开始研制，第一批粘土陶粒使用“土法工艺”法生产。随着时代的发展，新型墙体材料的研制越来越受到国家的重视，粘土的使用大量浪费可用耕地资源.人工制造的轻骨料及其制品的发展越来越快，若使用粘土制备陶粒还是造成粘土资源的浪费，为了节约粘土资源，保护环境，国家提出应禁止使用实心粘土砖及其其他粘土制品，使用淤泥及其页岩制备陶粒成为国家发展新型墙体材料的重点。要扩大生产页岩陶粒和淤泥陶粒，促进人造轻骨料更上一层楼。</p>' +
            '<p>粘土是有粘土矿物自然形成的具有可塑性，具有良好的膨胀性能的沉积物。粘土的分类大致有以下几种：黄土和类黄土粘土;淤泥类粘土，多是原生粘土经过风化、搬运与沉积而迁移到其它地方而形成;山土类，多生成于丘陵地带，属于原生粘土的一种;页、泥岩类粘土，为固结状态，泥岩呈块状等。组成粘土的颗粒大小不同，矿物种类和化学成分不同，物理、化学性质也不相 同。通常粘土中粒组的划分为：小于51ma的粘粒，5"---509m的粉粒，大于501.tm的砂 粒。粒径在51.tm以下的粘土矿物，比表面积大，是矿物成分中最活跃的成分，因此粘 土具有可塑性和焙烧性能。焙烧性能越好的粘土，颗粒粒径较小，具有优良的均匀性，普遍认为具有理想焙烧性能的粘土的组成为：粒径小于51ma>50%，粒径为5"-501ma >25%，粒径大于501ttrn<25%。</p>' +
            '</div>' +
            '</div>'
          },
          {
            type: 5,
            content: '<div class="article">' +
            '<h3 class="articleTit">陶粒的构成特点及功能？</h3>' +
            '<div class="sub_info line">' +
            '<span>发布日期：2018-12-19 14:49</span> ' +
            '<span>点击量：544</span>' +
            '</div>' +
            '<div class="articleCon">' +
            '<p>小编也是一个很爱好花花草草的人，在花草养殖过程中了解到陶粒这种物体。我们日常看到的陶粒的外观特征大部分呈圆形或椭圆形球体，但也有一些仿碎石陶粒不是圆形或椭圆形球体，而呈不规则碎石状。陶粒形状因工艺不同而各异。它的表面是一层坚硬的外壳，这层外壳呈陶质或釉质，具有隔水保气作用，并且赋予陶粒较高的强度。因为生产陶粒的原料很多，陶粒的品种也很多，因而颜色也就很多。焙烧陶粒的颜色大多为暗红色、赭红色，也有一些特殊品种为灰黄色、灰黑色、灰白色、青灰色等。免烧陶粒因所用固体废弃物不同，颜色各异，一般为灰黑色，表面没有光泽度，不如焙烧陶粒光滑。</p>' +
            '<p>轻质性是陶粒许多优良性能中最重要的一点，也是它能够取代重质砂石的主要原因。陶粒的内部结构特征呈细密蜂窝状微孔。这些微孔都是封闭型的，而不是连通型的。它是由于气体被包裹进壳内而形成的，这是陶粒质轻的主要原因。</p>' +
            '<p>陶粒的细小颗粒部分称为陶砂。在陶粒中有许多小于5㎜的细颗粒，在生产中用筛分机将这部分细小颗粒筛分出来，习惯上称之为陶砂。陶砂的密度略高，化学和热稳定性好。陶砂主要用于代替天然河砂或山砂配制轻集料混凝土、轻质砂浆，也可作耐酸、耐热混凝土细集料。主要品种有黏土陶砂页岩陶砂和粉煤灰陶砂等。使用陶砂的目的也是为降低建筑物自重。陶砂也可用于无土栽培和工业过滤。</p>' +
            '</div>' +
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
            path: `/product/${key}`
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
      selectProduct(key, keyPath){
        this.$router.push({
          path: `/product/${key}`
        });
      },
      selectNews(key, keyPath){
        for (let i = 0; i < this.articleList.length; i++) {
          if (key == this.articleList[i].type) {
            this.content = this.articleList[i].content;
          }
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

  .product-nav div {
    line-height: 42px;
    height: 42px;
  }

  .product-main .el-menu {
    padding-left: 0;
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

  .news li {
    padding: 0 !important;
  }

  .article {
    float: left;
    width: 78%;
    margin-left: 12px;
  }

  .articleTit {
    font-size: 22px;
    color: #434343;
    text-align: center;
    height: 38px;
    font-weight: 400;
    line-height: 24px;
  }

  .sub_info.line {
    border-bottom: 1px solid #dddddd;
    padding-bottom: 10px;
    margin-bottom: 20px;
  }

  .sub_info {
    text-align: center;
    padding: 4px 0 5px;
    line-height: 19px;
    color: #434343;
  }

  .articleCon {
    line-height: 2em;
    color: #666;
  }

  .articleCon p {
    text-indent: 2em;
    line-height: 2em;
  }
</style>
