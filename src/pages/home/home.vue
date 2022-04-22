<template>
  <div>
   <home-header></home-header>
   <home-icons></home-icons>
  </div>
</template>

<script>
import HomeHeader from './commponents/Header'
import HomeIcons from './commponents/Icons'

export default{
  name: 'Home',
  components: {
    HomeHeader,
    HomeIcons
  }

}
</script>
<style>
</style>
