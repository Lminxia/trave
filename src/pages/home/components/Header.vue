<template>
  <div class="header">
    <div class="header-left">
      <div class="iconfont back-icon">&#xe624;</div>
    </div>
    <div class="header-input">
      <span class="iconfont">&#xe632;</span>
      输入城市/景点/游玩主题
      </div>
    <div class="header-right">
      城市<span class="iconfont down-icon">&#xe63b;</span>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HomeHeader'
}
</script>
<!--scoped使样式不会对其他组件有影响-->
<!--用了stylus语法，所以样式写法如下-->
<!--在reset.css文件中设置了html的font-size为50px,
所以1rem=html font-size = 50px-->
<!--@代表src目录，当在css中加入css,需要在前面添加~-->
<style lang="stylus" scoped>
  @import '~@/assets/styles/varibles.styl'
  .header
    display: flex
    line-height: .86rem
    background: $bgColor
    color: #fff
    .header-left
      width: .84rem
      float: left
      .back-icon
        text-align:center
    .header-input
      flex:1
      height: .64rem
      line-height: .64rem
      background: #fff
      border-radius: .1rem
      margin-top: .12rem
      padding-left: .14rem
      color: #ccc
    .header-right
      width: 1.24rem
      float: right
      text-align: center
      .down-icon
        font-size:.24rem
</style>
