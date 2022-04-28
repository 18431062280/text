<template>
  <div>
   <home-header></home-header>
   <home-swiper></home-swiper>
   <home-icons></home-icons>
   <home-recommend></home-recommend>
  <home-weekend></home-weekend>
  </div>
</template>

<script>
import HomeHeader from './commponents/Header'
import HomeSwiper from './commponents/Swiper'
import HomeIcons from './commponents/Icons'
import HomeRecommend from './commponents/Recommend'
import HomeWeekend from './commponents/Weekend'

export default{
  name: 'Home',
  components: {
    HomeHeader,
    HomeSwiper,
    HomeIcons,
    HomeRecommend,
    HomeWeekend

  }

}
</script>
<style>
</style>
