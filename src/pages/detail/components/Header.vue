<template>
  <div>
    <router-link
      tag='div' to='/'
      class="header-abs"
      v-show="showAbs"
      >
      <div class="iconfont back-icon">&#xe624;</div>
    </router-link>
    <div
      class="header-fixed"
      v-show="!showAbs"
      :style="opacityStyle"
      >
      <router-link tag='div' to='/'>
        <div class="iconfont back-fixed-icon">&#xe624;</div>
      </router-link>
      景点详情
    </div>
  </div>
</template>

<script>

export default {
  name: 'DetailHeader',
  data () {
    return {
      showAbs: true,
      opacityStyle: {
        opacity: 0
      }
    }
  },
  methods: {
    handleScroll () {
      const top = document.documentElement.scrollTop
      if (top > 25) {
        let opacity = top / 180
        opacity = opacity > 1 ? 1 : opacity
        this.opacityStyle = {
          opacity
        }
        this.showAbs = false
      } else {
        this.showAbs = true
      }
    }
  },
  activated () {
    window.addEventListener('scroll', this.handleScroll)
  },
  deactivated () {
    window.removeEventListener('scroll', this.handleScroll)
  }
}
</script>

<style lang="stylus" scoped>
  @import '~@/assets/styles/varibles.styl'
  .header-abs
    position: absolute
    left: .2rem
    top: .2rem
    width: .7rem
    height: .7rem
    line-height: .7rem
    text-align: center
    border-radius: .35rem
    background: rgba(0, 0, 0, .7)
    .back-icon
      color: #fff
      font-size: .3rem
  .header-fixed
    z-index:1
    position:fixed
    top: 0
    left: 0
    right: 0
    height: $headerHeight
    line-height: $headerHeight
    text-align: center
    color: #fff
    background: $bgColor
    font-size: .32rem
    .back-fixed-icon
      position:absolute
      top: 0
      left: .26rem
      color: #fff
</style>
