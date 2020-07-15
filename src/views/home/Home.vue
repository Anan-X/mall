<template>
  <div>
    <!-- 导航栏 -->
    <nav-bar class="cart-nav-background">
      <slot slot="center">购物街</slot>
    </nav-bar>
    <!-- 轮播图 -->
    <home-swiper 
    :banners="banners" />
    <!-- 推荐 -->
    <recommends-view 
    :recommends="recommends" />
  </div>

</template>

<script>
import NavBar from 'components/common/navbar/NavBar'
import HomeSwiper from 'views/home/childcomps/HomeSwiper'
import RecommendsView from './childcomps/RecommendView'

import {getHomeMultidata} from 'network/home'
export default {
  data () {
    return {
      banners: [],
      recommends: [],
    }
  },
  components: {
    NavBar,
    HomeSwiper,
    RecommendsView
  },
  created () {
    getHomeMultidata().then(res => {
      console.log(res)
      this.banners = res.data.data.banner.list
      this.recommends = res.data.data.recommend.list
    }).catch(err => console.log(err))
  }
}
</script>

<style>
  .cart-nav-background {
    background-color: var(--color-tint);
    color: var(--color-background);
  }
</style>
