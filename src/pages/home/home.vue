<template>
  <div>
   <home-header ></home-header>
   <home-swiper :list="swiperList"></home-swiper>
   <home-icons :list="iconList"></home-icons>
   <home-recommend :list="recommendList"></home-recommend>
  <home-weekend :list="weekendList"></home-weekend>
  </div>
</template>

<script>
import HomeHeader from './commponents/Header'
import HomeSwiper from './commponents/Swiper'
import HomeIcons from './commponents/Icons'
import HomeRecommend from './commponents/Recommend'
import HomeWeekend from './commponents/Weekend'
import axios from 'axios'
import { mapState } from 'vuex'

export default{
  name: 'Home',
  components: {
    HomeHeader,
    HomeSwiper,
    HomeIcons,
    HomeRecommend,
    HomeWeekend
  },
  data () {
    return {
     lastCity: '',
      swiperList: [],
      iconList: [],
      recommendList: [],
      weekendList: [],
      
    }
  },
  computed:{
    ...mapState(['city'])
  },
  methods: {
    getHomeInfo () {
      axios.get('/api/index.json?city='+this.city)
        .then(this.getHomeInfoSucc)
    },
    getHomeInfoSucc (res) {
      res = res.data
      if(res.ret && res.data){
      
        this.swiperList = res.data.swiperList
        this.iconList = res.data.iconList
        this.recommendList = res.data.recommendList
        this.weekendList = res.data.weekendList
      }
    },

   
  //   //获取电竞和旅游
  //   getgame(){
  //      let newVar=axios.create({
  //       baseURL:'http://api.tianapi.com/',
  //       timeout:5000
  //   });
  //   //电竞
  //   newVar({
  //       url:'esports/index',
  //       params:{
  //           key: '57468839d455f195e45a1b6aa2c931ff',
  //           num: 3
  //       }
  //   }).then(res=>{
  //      this.recommendList = res.data.newslist
  //   }),
  //   //旅游
  // newVar({
  //       url:'travel/index',
  //       params:{
  //           key: '57468839d455f195e45a1b6aa2c931ff',
  //           num: 5
  //       }
  //   }).then(res=>{
  //       this.weekendList = res.data.newslist
  //   })
  
  //   }
  },
  mounted () {

    this.lastCity = this.city
    this.getHomeInfo()
    // ,
    // this.getgame()

  },
  activated () {
    if(this.lastCity !== this.city){
      this.lastCity = this.city
      this.getHomeInfo()
    }
  }

}
</script>
<style>
</style>
