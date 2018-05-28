<template>
  <div class="wrapper">
    <swiper :options="swiperOption" >
      <!-- slides -->
      <swiper-slide  v-for="item of swiperList" :key="item.id">
        <img class="swipe-img" :src="item.imgUrl"  alt="去哪儿门票" style="opacity: 1;">
      </swiper-slide>
      <!-- Optional controls -->
      <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeSwiper',
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true
      },
      swiperList: [{
        id: '01',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1805/3b/ef86879aa50e3002.jpg_750x200_2a108508.jpg'
      },
      {
        id: '02',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1805/10/3ee6df72beb86402.jpg_750x200_e02a4c99.jpg'
      }]
    }
  }
}
</script>

<!--scoped使样式不影响其他组件，而swiper-pagination-bullet-active是其他组件的class，
因此想修改它需要用>>>进行穿透-->
<style lang="stylus" scoped>
  .wrapper >>> .swiper-pagination-bullet-active
    background: #fff
  .wrapper
    overflow: hidden
    width: 100%
    height: 0
    padding-bottom: 26.67%
    background: #eee
    .swipe-img
      width: 100%
</style>
