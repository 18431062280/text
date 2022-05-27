<template>
  <div>
      <detai-banner 
      :sightName="sightName"
      :bannerImg="bannerImg"
      :bannerImgs="gallaryImgs"
      :categoryList="categoryList"
      ></detai-banner>
      <detai-header></detai-header>
      <div class="content">
        <detai-list :list="list"></detai-list>
      </div>
  </div>
</template>

<script>
import DetaiBanner from './commponents/Banner'
import DetaiHeader from './commponents/Header'
import DetaiList from './commponents/List'
import axios from 'axios'

export default {
    name:'Detail',
    components:{
      DetaiBanner,
      DetaiHeader,
      DetaiList
    },
    data() {
      return{
        sightName: '',
        bannerImg:'',
        gallaryImgs:'',
        categoryList:'',
        list: [{
          title: '成人票',
          children: [{
            title:'成人三管联票',
            children: [{
              title:'成人三管联票-连锁店',
            }]
          },{
            title:'成人五管联票'
          }]
        },{
          title: '学生票'
        },{
          title: '儿童票'
        },{
          title: '特惠票'
        }]

      }
    },
    methods:{
      getDetailInfo(){
          axios.get('/api/detail.json?',{
            params: {
              id:this.$route.params.id
            }
          }).then(this.handleGetDataSucc)
      },
      handleGetDataSucc(res){
        res = res.data 
        if(res.ret && res.data) {
          const data = res.data 
          this.sightName = data.sightName
          this.bannerImg = data.bannerImg
          this.gallaryImgs = data.gallaryImgs
          this.categoryList = data.categoryList
        }
      }
    },
    mounted(){
      this.getDetailInfo()
    },
    
    
}
</script>

<style lang="stylus" scoped>
.content
  height: 50rem

</style>