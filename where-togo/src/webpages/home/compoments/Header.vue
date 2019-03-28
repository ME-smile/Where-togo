<template>
  <div class="header">
    <div class="header-left">
        <span class="iconfont back-icon">&#xe624;</span>
    </div>
    <div class="header-mid">
        <span class="iconfont">&#xe632;</span>
        输入城市景点/游玩主题
    </div>
    <div class="header-right">
        南昌
        <span class="iconfont down-arrow">&#xe64a;</span>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HomeHeader',
  props: {
    city: String
  }
}
</script>

<style lang="stylus" scoped>
@import '~S/vars.styl'
.header
    display: flex
    line-height: .86rem
    background: $bgc
    color: #fff
    .header-left
        width: .64rem
        float: left
        .back-icon
            text-align: center
            font-size: .4rem
    .header-mid
        flex: 1
        line-height: .64rem
        height: .64rem
        background: #fff
        border-radius: .1rem
        margin-left: .2rem
        margin-top: .12rem
        padding-left: .2rem
        color: #ccc
    .header-right
        width: 1.24rem
        float: right
        text-align: center
        .down-arrow
            font-size: .24rem
</style>
