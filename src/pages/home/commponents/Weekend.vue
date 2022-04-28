<template>
  <div>
      <div class="title">热门推荐</div>
      <ul>
          <li class="item border-bottom" v-for="item of recommendList" :key="item.id">
                  <div class="item-img-warter">
                     <img class="item-img" :src="item.imgUrl" alt="">
                 </div>
              <div class="item-info">
                <p class="item-title">{{item.title}}</p>
                <p class="item-desc">{{item.desc}}</p>
              
              </div>
          </li>
      </ul>
  </div>
</template>

<script>
export default {
    name: "HomeWeekend",
    data () {
      return {
         recommendList: [{
        id: '0001',
        imgUrl: 'https://imgs.qunarzz.com/sight/source/1703/eb/abf0bf07ab6f80.jpg_r_640x214_e15a3ac8.jpg',
        title: '邯郸方特国色春秋',
        desc: '浪漫邯郸，浪漫邯郸方特国色春秋'
      },{
        id: '0002',
        imgUrl: 'https://imgs.qunarzz.com/sight/source/1703/eb/abf0bf07ab6f80.jpg_r_640x214_e15a3ac8.jpg',
        title: '邯郸方特国色春秋',
        desc: '浪漫邯郸，浪漫邯郸方特国色春秋'
      },{
        id: '0003',
        imgUrl: 'https://imgs.qunarzz.com/sight/source/1703/eb/abf0bf07ab6f80.jpg_r_640x214_e15a3ac8.jpg',
        title: '邯郸方特国色春秋',
        desc: '浪漫邯郸，浪漫邯郸方特国色春秋'
      }]
      }
    }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/minxins.styl'

.title
  margin-top: .2rem
  line-height: .8rem
  background: #eee
  text-indent: .2rem
.item-img-warter
  overflow: hidden
  height: 0
  padding-bottom: 33.9%
  .item-img
    width: 100%
  .item-info
    padding: .1rem
	.item-title
		line-height: .54rem
		font-size: .32rem
		ellipsis()
	.item-desc
		line-height: .4rem
		color: #ccc
		ellipsis()

</style>