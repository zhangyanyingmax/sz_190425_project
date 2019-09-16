<template>
  <div id="app">
    <ele-header></ele-header>
    <nav>
      <div>
        <router-link to="/goods">商品</router-link>
      </div>
      <div>
        <router-link to="/ratings">评价</router-link>
      </div>
      <div>
        <router-link to="/shops">商家</router-link>
      </div>
    </nav>
    <router-view></router-view>
  </div>
</template>

<script>
import axios from "axios";
import header from "components/ele-header/ele-header.vue"
export default {
  name: 'app',
  components:{
      "ele-header":header
  },
  async created(){
      const  seller = await  axios.get("/seller")
  }
}
</script>

<style lang="stylus" rel="stylesheet/stylus" scoped>
@import "./common/stylus/mixin.styl"
#app
  nav
    border-1px(rgba(7,17,27,.1))
    display flex
    height 40px
    & > div
      flex 1
      text-align center
      line-height 40px
      a
        font-size 14px
        color rgb(77,85,93)
        display block
        width 100%
        height 100%
        &.active
          color rgb(240,20,20)
</style>
