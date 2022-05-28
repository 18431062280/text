<template>
  <div>
      <div class="banner" @click="handleBanner">
      <img class="banner-img" :src="bannerImg">

      <div class="banner-info"> 
          <div class="banner-tittle">
            {{this.sightName}}
            </div>
          <div class="banner-number">
             <span class="iconfont banner-icon">&#xe8d3;</span>
             {{this.bannerImgs.length}}
          </div>
      </div>
    </div>
    <fade-animation>
  <common-gallary :imgs="bannerImgs" v-show="showGallary" @close="handleGallaryClose"></common-gallary>
  </fade-animation>
  </div>
</template>

<script>
import CommonGallary from 'common/gallary/Gallary.vue'
import FadeAnimation from 'common/fade/FadeAnimation'


export default {
    name:'Detail',
    props: {
      sightName: String,
      bannerImg:String,
      bannerImgs:Array,
      FadeAnimation

    },
    data () {
      return {
        showGallary: false,
       
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
    FadeAnimation
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
