<template>
  <div class="wrapper">
    <swiper :options="swiperOption">
    <swiper-slide v-for="item of swiperImgList" :key="item.id">
        <img class="swiper-img" :src="item.img_url">
    </swiper-slide>
    <div class="swiper-pagination" slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default{
  name: 'HomeSwiper',
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true
      },
      swiperImgList: [
        {
          id: 'img01',
          img_url: 'https://img1.qunarzz.com/order/comp/1805/2e/6e407f088bfb902.png'
        },
        {
          id: 'img02',
          img_url: 'https://img1.qunarzz.com/order/comp/1805/2e/6e407f088bfb902.png'
        }
      ]
    }
  }
}
</script>

<style lang="stylus" scoped>
.wrapper >>> .swiper-pagination-bullet-active
  background: #fff
.wrapper
  overflow: hidden
  width: 100%
  height: 0
  padding-bottom: 24.25%
  background: #eee;
  .swiper-img
    width: 100%
</style>
