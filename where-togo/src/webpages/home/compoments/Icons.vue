<template>
    <div class='icons-area'>
     <!--  实现图标翻页 -->
      <swiper :options='swiperOption'>
        <swiper-slide v-for='(page,index) of pages' :key='index'>
          <div class='icon' v-for='item of page' :key='item.id'>
              <div class='icon-content'>
                  <img class='icon-img' :src='item.imgUrl'>
              </div>
              <p class='icon-desc'>{{ item.desc }}</p>
          </div>
        </swiper-slide>
      </swiper>
    </div>
</template>

<script>
export default {
  name: 'HomeIcons',
  props: {
    list: Array
  },
  data () {
    return {
      swiperOption: {
        autoplay: false
      }
    }
  },
  computed: {
    pages () {
      const pages = []
      this.list.forEach((item, index) => {
        const page = Math.floor(index / 8)
        if (!pages[page]) {
          pages[page] = []
        }
        pages[page].push(item)
      })
      return pages
    }
  }
}
</script>

<style lang='stylus' scoped>
@import '~S/mixins.styl'
@import '~S/vars.styl'
.icons >>> .swiper-container
  height: 0
  padding-bottom: 50%
.icons-area
  margin-top: .1rem
  overflow: hidden
  height: 0
  padding-bottom: 50%
  .icon
    position: relative
    overflow: hidden
    float: left
    width: 25%
    padding-bottom: 25%
    .icon-content
      position: absolute
      top: 0
      left: 0
      right: 0
      bottom: .44rem
      box-sizing: border-box
      padding: .1rem
      .icon-img
        display: block
        margin: 0 auto
        height: 100%
    .icon-desc
      position: absolute
      left: 0
      right: 0
      bottom: 0
      height: .44rem
      line-height: .44rem
      text-align: center
      color: $darkTextColor
      ellipsis()
</style>
