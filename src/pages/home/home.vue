<template>
  <div>
   <home-header></home-header>
   <home-swiper></home-swiper>
   <home-icons></home-icons>
  </div>
</template>

<script>
import HomeHeader from './commponents/Header'
import HomeSwiper from './commponents/Swiper'
import HomeIcons from './commponents/Icons'


export default{
  name: 'Home',
  components: {
    HomeHeader,
    HomeSwiper,
    HomeIcons
  }

}
</script>
<style>
</style>
