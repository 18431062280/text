<template>
  <div class="wrapper">
    <swiper :options="swiperoption" >
        <swiper-slide>
            <img class="swiper-img" src="../../../assets/add1.jpeg" alt="">
        </swiper-slide>
        <swiper-slide>
            <img class="swiper-img" src="../../../assets/add2.jpeg" alt="">
        </swiper-slide>
        
        <div class="swiper-pagination" slot="pagination"></div>
  </swiper>
  </div>
</template>

<script>
export default {
    name: 'HomeSwiper',
    data () {
        return{
            swiperoption: {
                pagination: '.swiper-pagination',
                loop: true
            }
        }
    }
}
</script>

<style lang="stylus" scoped>
    .wrapper >>> .swiper-pagination-bullet-active
        background: #fff !important
    .wrapper
      overflow: hidden
      height: 0
      width: 100%
      padding-bottom: 31.25%
      background: #eee
      
      .swiper-img
        width: 100%
</style>