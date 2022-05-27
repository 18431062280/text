<template>
  <div>
      <div class="banner" @click="handleBanner">
      <img class="banner-img" src="http://img1.qunarzz.com/sight/p0/1805/78/789e31213399290fa3.water.jpg_600x330_a807626a.jpg">

      <div class="banner-info"> 
          <div class="banner-tittle">
            白石山世界地质公园(AAAAA景区)
            </div>
          <div class="banner-number">
             <span class="iconfont banner-icon">&#xe8d3;</span>39
          </div>
      </div>
    </div>
  <common-gallary :imgs="imgs" v-show="showGallary" @close="handleGallaryClose"></common-gallary>
  </div>
</template>

<script>
import CommonGallary from 'common/gallary/Gallary.vue'

export default {
    name:'Detail',
    data () {
      return {
        showGallary: false,
        imgs: ['http://img1.qunarzz.com/sight/p0/1805/78/789e31213399290fa3.water.jpg_r_800x800_c8320f98.jpg',
            'http://img1.qunarzz.com/sight/p0/1805/1e/1ead31f6005d012a3.img.png_r_800x800_05202bdc.png']
      }
    },
    methods:{ 
      handleBanner(){
        this.showGallary=true
      },
      handleGallaryClose(){
        this.showGallary=false
      }
    },
    components: {
      CommonGallary,
    }
}
</script>

<style lang="stylus" scoped>
  .banner
    position relative
    overflow: hidden
    height: 0
    padding-bottom: 55%
    .banner-img 
      width: 100%
    .banner-info
      display: flex
      position absolute
      left: 0
      right: 0
      bottom: 0
      line-height: .6rem
      color: #fff
      margin-left: .2rem
      background-image: linear-gradient(top,rgba(0,0,0,0),rgba(0,0,0,0.8))
      .banner-title 
        flex: 1
        font-size: .32rem 
        padding: 0 .2rem
       
      .banner-number
        position absolute
        right:.1rem
        margin-top: .1rem
        padding: 0 .4rem 
        height: .32rem 
        line-height: .32rem 
        border-radius: .2rem 
        background: rgba(0,0,0,.8)
        font-size: .32rem 
        .banner-icon
          font-size: .24rem
</style>
