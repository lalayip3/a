<template>
  <div>
    <div class="title">一手新盤</div>
    <ul>
      <router-link
        tag="li"
        class="item border-bottom clearfix"
        v-for="item of list"
        :key="item.id"
        :to="'/detail/' + item.id"
      >
        <img class="item-img" :src="item.imgUrl" />
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
          <button class="item-button">查看詳情</button>
        </div>
      </router-link>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeRecommend',
  props: {
    list: Array
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/mixins.styl'
  .title
    margin-top: .2rem
    line-height: .8rem
    background: #eee
    text-indent: .2rem
    border 1px solid lightgray
    color darkred
  .item
    /*overflow: hidden*/
    /*display: flex*/
    /*height: 1.9rem*/
    width 100%
    height 40%
    border-bottom 1px solid gray
  .item.clearfix:after {
      visibility: hidden;
      display: block;
      font-size: 0;
      content: " ";
      clear: both;
      height: 0;
    }
  .item-img
      /*flex 1*/
      /*width: 1.7rem*/
      /*height: 1.7rem*/
      padding: .1rem
      width 60%
      height 100%
      /*height 80%*/
      float left
  .item-info
      /*flex: 1*/
      /*width 40*/
      padding: .1rem
      float right
      min-width: 0
      margin-right 25px
      margin-top 35px
      /*text-align center*/
      /*margin 0 auto*/
      .item-title
        line-height: .54rem
        font-size: .32rem
        ellipsis()
      .item-desc
        /*margin-top 20%*/
        line-height: .4rem
        color: #ccc
        ellipsis()
      .item-button
        line-height: .44rem
        margin-top: .16rem
        background: #ff9300
        padding: 0 .2rem
        border-radius: .06rem
        color: #fff
</style>
