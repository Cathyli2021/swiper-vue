<template>
  <div class="vue-swiper">
    <h1>{{ msg }}</h1>
    <div class="container">
      <swiper
        :options="swiperOption"
        ref="mySwiper"
        class="swiper-container-no-flexbox"
      >
      <!-- 这种写法也可以 -->
        <!-- <swiper-slide>
          <img src="../../static/images/1.jpg" alt class="1">
        </swiper-slide>
        <swiper-slide>
          <img src="../../static/images/2.jpg" alt class="2">
        </swiper-slide>
        <swiper-slide>
          <img src="../../static/images/3.jpg" alt class="3">
        </swiper-slide>
        <swiper-slide>
          <img src="../../static/images/4.jpg" alt class="4">
        </swiper-slide>
        <swiper-slide>
          <img src="../../static/images/5.jpg" alt class="5">
        </swiper-slide> -->
        
        <!-- 这种写法更常见 -->
        <swiper-slide v-for="(item, index) in bugs1" :key="index">
          <img class="swiper-img" :src="item" alt="" />
        </swiper-slide>
      </swiper>
    </div>
  </div>
</template>

<script>
import Vue from "vue";
import VueAwesomeSwiper from "vue-awesome-swiper";
Vue.use(VueAwesomeSwiper);
import Swiper from "swiper";

export default {
  name: "vueSwiper",
  data() {
    return {
      msg: "Vue-swiper",
      swiperOption: {
        notNextTick: true,
        loop: true,  // 启循环模式，即滑动到最后一个 slide 后会自动切换到第一个 slide。
        slidesPerView: 3,
        centeredSlides: true,
        autoplay: {
          delay: 2000, // 自动播放间隔时间，单位为毫秒
          disableOnInteraction: false, // 用户操作后是否停止自动播放
        },
        forceToAxis: true, //鼠标竖向滚动无法控制横向切换
        slideToClickedSlide: true, //设置为true则点击slide会过渡到这个slide。
        grabCursor: true,  // 当鼠标位于 swiper 上时显示抓取样式。
        setWrapperSize: true,  // 根据 slides 的尺寸自动调整容器的尺寸。
        mousewheelControl: true,  // 开启鼠标滚轮控制 swiper。
        observeParents: true,  // 如果 swiper 元素有父级元素，并且父级元素的尺寸发生变化时，swiper 会重新初始化。
        
      },
      bugs1: [
        "http://g.hiphotos.baidu.com/zhidao/pic/item/c83d70cf3bc79f3d6e7bf85db8a1cd11738b29c0.jpg",
        "http://big5.wallcoo.com/photograph/summer_feeling/images/%5Bwallcoo.com%5D_summer_feeling_234217.jpg",
        "https://img0.baidu.com/it/u=4281860672,1981139753&fm=253&fmt=auto&app=138&f=JPEG?w=480&h=320",
        "https://img0.baidu.com/it/u=2862534777,914942650&fm=253&fmt=auto&app=138&f=JPEG?w=889&h=500",
        "https://img0.baidu.com/it/u=2862534777,914942650&fm=253&fmt=auto&app=138&f=JPEG?w=889&h=500",
        "https://img0.baidu.com/it/u=2862534777,914942650&fm=253&fmt=auto&app=138&f=JPEG?w=889&h=500",
      ],
    };
  },
};
</script>


<style lang="scss" scoped>
// .container {
//   // width: 500px;
//   overflow: hidden;
//   margin: 0 auto;
//   border: 1px solid #000;
// }
// img {
//   max-width: 100%;
//   display: block;
// }
// .swiper-slide-shadow-right,
// .swiper-slide-shadow-left {
//   background-image: none !important;
//   opacity: 0 !important;
// }

// .swiper-slide {
//   transform: scale(0.7);
//   transition: all 0.3s linear;
// }
// .swiper-slide.swiper-slide-active {
//   transform: scale(1);
// }
@import "../../node_modules/swiper/dist/css/swiper.min.css";
</style>