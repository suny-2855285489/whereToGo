<template lang="html">
  <div class="detaillist">
    <div class="item" v-for="(item,index) of categoryList" :key="index">
      <div class="item-title border-topbottom">
        <span class="item-title-icon"></span>
        {{item.title}}
      </div>
      <div class="item-children" v-if="item.children">
        <detaillist :list="item.children">{{item.children}}</detaillist>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "detaillist",
  props: {
    categoryList:Array
  }
}
</script>

<style lang="stylus" scoped>
@import "~styles/varibies.styl"
.item-title
    line-height .8rem
    font-size .32rem
    padding 0 .2rem
    .item-title-icon
        position relative
        left .06rem
        top .06rem
        display inline-block
        width .36rem
        height .36rem
        background url(http://s.qunarzz.com/piao/image/touch/sight/detail.png) 0 -0.45rem no-repeat
        margin-right .1rem
        background-size .4rem 3rem
.item-children
    margin-left .4rem

</style>
