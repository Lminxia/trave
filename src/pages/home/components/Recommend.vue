<template>
  <div>
    <div class="title">
      热销推荐
    </div>
    <ul>
      <li class="item" v-for="item of recommentList" :key="item.id">
        <img class="item-img" :src="item.imgUrl" alt="长隆水上乐园">
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
          <button class="item-btn">查看详情</button>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeRecomment',
  data () {
    return {
      recommentList: [{
        id: '01',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1707/ab/abb70c851caaa6d8a3.img.jpg_200x200_b902dd9e.jpg',
        title: '长隆水上乐园',
        desc: '254545条评论'
      }, {
        id: '02',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1709/41/411f234d79457081a3.img.jpg_200x200_ea02ef99.jpg',
        title: '长隆野生动物园',
        desc: '234345条评论'
      }, {
        id: '03',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1805/f6/f65914357903b096a3.img.jpg_200x200_2c394f76.jpg',
        title: '正佳自然科学博物馆',
        desc: '123354条评论'
      }]
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~@/assets/styles/mixins.styl'
  .title
    margin-top: .2rem
    line-height: .8rem
    background: #eee
    text-indent: .2rem
  .item
    overflow: hidden
    display: flex
    height: 1.9rem
    .item-img
      width: 1.7rem
      height: 1.7rem
      margin: .1rem
    .item-info
      flex:1
      padding: .1rem
      min-width: 0
      .item-title
        line-height: .54rem
        font-size: .32rem
        ellipsis()
      .item-desc
        line-height: .4rem
        color: #ccc
        ellipsis()
      .item-btn
        background: #ff9300
        padding: 0 .1rem
        border-radius: .06rem
        color: #fff
        margin-top: .16rem
        line-height: .44rem
</style>
