<template>
  <div style="height:100%;position: relative">
    <div class="search">
      <headsearch></headsearch>
    </div>
    <div class="scrollContainer">
      <scroll ref="scroll" class="scroll-content" style="height:100%">
        <div class="index_cont">
          <div class="cont_top">
            <div class="imgScroll">
              <Swiper :list="scrollImgs" :auto="true" :loop="true" :height="swiperHeight"></Swiper>
            </div>
            <!-- <div class="movement">
                                                  <img src="./img/menu.png" alt="userImg">
                                                  <div class="scrollFont">
                                                    <marquee>
                                                      <marquee-item v-for="i in 5" :key="i" @click.native="onClick(i)" class="align-middle">hello world {{i}}
                                                      </marquee-item>
                                                    </marquee>
                                                  </div>
                                                </div> -->
            <ul class="top_btn">
              <li @click="toClassPage(1)"><img src="./font/quane.svg" alt="">
                <span>全额返</span>
              </li>
              <li @click="toClassPage(2)"><img src="./font/chaoe.svg" alt=" ">
                <span>超额返</span>
              </li>
              <li @click="toClassPage(3)"><img src="./font/jinbi.svg" alt="">
                <span>金币拿</span>
              </li>
              <li @click="toClassPage(4)"><img src="./font/plus.svg" alt=" ">
                <span>Plus专享</span>
              </li>
              <li @click="toClassPage(5)"><img src="./font/help.svg" alt="">
                <span>新手指引</span>
              </li>
            </ul>
          </div>
          <div class="cont_show1">
            <div class="cont_show_title" style="background-image:url(http://img4.imgtn.bdimg.com/it/u=3933909600,1773650585&fm=214&gp=0.jpg)">
              <h2 class="m_title">抽商品欧皇就是你</h2>
              <span class="m_all" @click="toClassPage(1)">查看全部&nbsp;&gt;</span>
            </div>
            <div class="cont_show_scroll">
              <slider class="scroll-content" :arr="arrImg1" :defaultUnit="defaultUnit" :defaultWidth="defaultWidth" :defaultMargin="defaultMargin">
                <div class="scroll_item" v-for="(item, index) in arrImg1" @click="goDetail(item)" :key="index">
                  <merchandise :obj="item"></merchandise>
                </div>
              </slider>
            </div>
          </div>
          <div class="cont_show1">
            <div class="cont_show_title" style="background-image:url(http://img.bbs.wisenjoy.com/forum/201401/05/084533euz37f1lvh1juku1.jpg)">
              <h2 class="m_title">必中爱上就不错过</h2>
              <span class="m_all" @click="toClassPage(3)">查看全部&nbsp;&gt;</span>
            </div>
            <div class="cont_show_scroll">
              <slider class="scroll-content" :arr="arrImg2" :defaultUnit="defaultUnit" :defaultWidth="defaultWidth" :defaultMargin="defaultMargin">
                <div class="scroll_item" v-for="(item, index) in arrImg2" @click="goDetail(item)" :key="index">
                  <merchandise :obj="item"></merchandise>
                </div>
              </slider>
            </div>
          </div>
          <div class="cont_show2">
            <h2 class="m_title" @click="toClassPage(0)">优质商品
              <span>白拿</span>到手软&nbsp;&gt;</h2>
            <div class="cont_show_scroll">
              <div class="scroll_item" v-for="(item, index) in arrImg3" @click="goDetail(item)" :key="index">
                <merchandise :obj="item"></merchandise>
              </div>
            </div>
          </div>
          <div class="cont_show1">
            <h3 @click="toClassPage(0)">潮流女装&nbsp;&gt;</h3>
            <div class="cont_show_title">
              <img src="http://img2.imgtn.bdimg.com/it/u=4095006314,944966500&fm=214&gp=0.jpg" alt="">
            </div>
            <div class="cont_show_scroll">
              <slider class="scroll-content" :arr="arrImg4" :defaultUnit="defaultUnit" :defaultWidth="defaultWidth" :defaultMargin="defaultMargin">
                <div class="scroll_item" v-for="(item, index) in arrImg4" @click="goDetail(item)" :key="index">
                  <merchandise :obj="item"></merchandise>
                </div>
              </slider>
            </div>
          </div>
          <div class="cont_show1">
            <h3 @click="toClassPage(0)">时尚男装&nbsp;&gt;</h3>
            <div class="cont_show_title">
              <img src="http://pic.qiantucdn.com/58pic/19/76/32/571241ca47377_1024.jpg" alt="">
            </div>
            <div class="cont_show_scroll">
              <slider class="scroll-content" :arr="arrImg5" :defaultUnit="defaultUnit" :defaultWidth="defaultWidth" :defaultMargin="defaultMargin">
                <div class="scroll_item" v-for="(item, index) in arrImg5" @click="goDetail(item)" :key="index">
                  <merchandise :obj="item"></merchandise>
                </div>
              </slider>
            </div>
          </div>
        </div>
      </scroll>
    </div>
  </div>
</template>
<script type="text/ecmascript-6">
import Headsearch from '../../base/headsearch/headsearch'
import Scroll from '../../base/scroll/scroll'
import Slider from '../../base/slider/slider'
import { Swiper, Marquee, MarqueeItem, Alert } from 'vux'
import Merchandise from '../../base/merchandise/merchandise_1'

export default {
  name: 'index',
  components: {
    Headsearch,
    Swiper,
    Marquee,
    MarqueeItem,
    Merchandise,
    Scroll,
    Slider,
    Alert
  },
  data () {
    return {
      scrollX: true,
      arrImg1: [
        {
          imgSrc: 'http://baoyitech.oss-cn-hangzhou.aliyuncs.com/1508758557625c601fdea9f4b5fdf805d07334d1aff77',
          vip: 0,
          info: 'HeadImg',
          progress: '20',
          sellerTaskId: 'UN201710290180926516',
          msg: { pric: '20', state: '0', zhuan: '2', baina: '白拿' }
        },
        {
          imgSrc: 'http://baoyitech.oss-cn-hangzhou.aliyuncs.com/1508758557625c601fdea9f4b5fdf805d07334d1aff77',
          vip: 0,
          info: 'HeadImg',
          progress: '20',
          sellerTaskId: 'UN201710290180926516',
          msg: { pric: '20', state: '0', zhuan: '2', baina: '白拿' }
        },
        {
          imgSrc: 'http://baoyitech.oss-cn-hangzhou.aliyuncs.com/1508758557625c601fdea9f4b5fdf805d07334d1aff77',
          vip: 0,
          info: 'HeadImg',
          progress: '20',
          sellerTaskId: 'UN201710290180926516',
          msg: { pric: '20', state: '0', zhuan: '2', baina: '白拿' }
        },
        {
          imgSrc: 'http://baoyitech.oss-cn-hangzhou.aliyuncs.com/1508758557625c601fdea9f4b5fdf805d07334d1aff77',
          vip: 0,
          info: 'HeadImg',
          progress: '20',
          sellerTaskId: 'UN201710290180926516',
          msg: { pric: '20', state: '0', zhuan: '2', baina: '白拿' }
        },
        {
          imgSrc: 'http://baoyitech.oss-cn-hangzhou.aliyuncs.com/1508758557625c601fdea9f4b5fdf805d07334d1aff77',
          vip: 0,
          info: 'HeadImg',
          progress: '20',
          sellerTaskId: 'UN201710290180926516',
          msg: { pric: '20', state: '0', zhuan: '2', baina: '白拿' }
        }
      ],
      arrImg2: [{
        imgSrc: 'http://baoyitech.oss-cn-hangzhou.aliyuncs.com/1508758557625c601fdea9f4b5fdf805d07334d1aff77',
        vip: 0,
        info: 'HeadImg',
        progress: '20',
        sellerTaskId: 'UN201710290180926516',
        msg: { pric: '20', state: '0', zhuan: '2', baina: '白拿' }
      }],
      arrImg3: [{
        imgSrc: 'http://baoyitech.oss-cn-hangzhou.aliyuncs.com/1508758557625c601fdea9f4b5fdf805d07334d1aff77',
        vip: 0,
        info: 'HeadImg',
        progress: '20',
        sellerTaskId: 'UN201710290180926516',
        msg: { pric: '20', state: '0', zhuan: '2', baina: '白拿' }
      }],
      arrImg4: [{
        imgSrc: 'http://baoyitech.oss-cn-hangzhou.aliyuncs.com/1508758557625c601fdea9f4b5fdf805d07334d1aff77',
        vip: 0,
        info: 'HeadImg',
        progress: '20',
        sellerTaskId: 'UN201710290180926516',
        msg: { pric: '20', state: '0', zhuan: '2', baina: '白拿' }
      }],
      arrImg5: [{
        imgSrc: 'http://baoyitech.oss-cn-hangzhou.aliyuncs.com/1508758557625c601fdea9f4b5fdf805d07334d1aff77',
        vip: 0,
        info: 'HeadImg',
        progress: '20',
        sellerTaskId: 'UN201710290180926516',
        msg: { pric: '20', state: '0', zhuan: '2', baina: '白拿' }
      }],
      defaultWidth: 13.9,
      defaultUnit: 'rem',
      defaultMargin: 0,
      scrollImgs: [{
        url: 'javascript:',
        img: 'https://ss0.bdstatic.com/94oJfD_bAAcT8t7mm9GUKT-xh_/timg?image&quality=100&size=b4000_4000&sec=1509517433&di=c0de1a6c7a86b4409f32a335c906343d&src=http://pic.58pic.com/58pic/17/35/16/60758PICtm5_1024.jpg'
      }, {
        url: 'javascript:',
        img: 'http://pic2.ooopic.com/13/19/36/88b4OOOPIC4d.jpg'
      }, {
        url: 'javascript:',
        img: 'http://image.tupian114.com/20160825/2016082509/09145367.jpg'
      }, {
        url: 'javascript:',
        img: 'http://pic2.ooopic.com/10/67/08/30b1OOOPICcb.jpg'
      }],
      swiperHeight: '12rem' // 轮播图高度
    }
  },
  methods: {
    // 获取首页轮播图
    getBannerImg () {
      let _this = this
      this.$axios.get('/api/homePage/getBanner').then(function (data) {
        if (data.data.code === '200') {
          let arrData = data.data.data
          if (!data.data.data) {
            return false
          }
          let imgArr = []
          for (let i = 0; i < arrData.length; i++) {
            imgArr.push({
              url: '/nopay/details?sellerTaskId=' + arrData[i].sellerTaskId,
              img: arrData[i].picUrl,
              sellerTaskId: arrData[i].sellerTaskId
            })
          }
          _this.scrollImgs = imgArr
        } else {
          _this.$vux.alert.show({
            title: '提示',
            content: '今日暂无广告',
            onShow () {
              console.log('Plugin: I\'m showing')
            },
            onHide () {
              console.log('Plugin: I\'m hiding')
            }
          })
        }
      }).catch(function (err) {
        console.log(err)
        _this.$vux.alert.show({
          title: '错误',
          content: '服务器错误,请重试❗',
          onShow () {
            console.log('Plugin: I\'m showing')
          },
          onHide () {
            console.log('Plugin: I\'m hiding')
          }
        })
      })
    },
    // 获取推荐的抽奖商品
    getRecommendLottery () {
      this.$axios.get('/api/homePage/getRecommendLottery').then((data) => {
        if (data.data.code === '200') {
          let arrList = []
          if (!data.data.data) {
            return false
          }
          for (let m of data.data.data) {
            let goods = {
              imgSrc: m.picUrl,
              hot: m.isRecommend,
              vip: m.isPlus,
              info: m.productName,
              progress: m.percent,
              sellerTaskId: m.sellerTaskId,
              msg: {
                pric: m.price,
                state: m.isMore,
                zhuan: m.extraGold,
                baina: '白拿'
              }
            }
            arrList.push(goods)
          }
          this.arrImg1 = arrList
          this.$nextTick(() => {
            this.$refs.scroll.refresh()
          })
        }
      }).catch(function (err) {
        console.log(err)
      })
    },
    // 获取推荐的必中商品
    getRecommendSure () {
      this.$axios.get('/api/homePage/getRecommendSure').then(function (data) {
        if (data.data.code === '200') {
          let arrList = []
          if (!data.data.data) {
            return false
          }
          for (let m of data.data.data) {
            let goods = {
              imgSrc: m.picUrl,
              hot: m.isRecommend,
              vip: m.isPlus,
              info: m.productName,
              progress: m.percent,
              sellerTaskId: m.sellerTaskId,
              msg: {
                pric: m.price,
                state: m.isMore,
                zhuan: m.extraGold,
                baina: '白拿'
              }
            }
            arrList.push(goods)
          }
          this.arrImg2 = arrList
          this.$nextTick(() => {
            this.$refs.scroll.refresh()
          })
        }
      }).catch((err) => {
        console.log(err)
      })
    },
    // 获取优质的白拿商品
    getQualityFree () {
      this.$axios.get('/api/homePage/getQualityFree').then((data) => {
        if (data.data.code === '200') {
          let arrList = []
          if (!data.data.data) {
            return false
          }
          for (let m of data.data.data) {
            let goods = {
              imgSrc: m.picUrl,
              hot: m.isRecommend,
              vip: m.isPlus,
              info: m.productName,
              progress: m.percent,
              sellerTaskId: m.sellerTaskId,
              msg: {
                pric: m.price,
                state: m.isMore,
                zhuan: m.extraGold,
                baina: '白拿'
              }
            }
            arrList.push(goods)
          }
          this.arrImg3 = arrList
          this.$nextTick(() => {
            this.$refs.scroll.refresh()
          })
        }
      }).catch((err) => {
        console.log(err)
      })
    },
    // 获取热门的商品品类的列表
    /* getRecommedProductByClass() {
      this.$axios.post('api/homePage/getRecommedProductByClass', {
        productClassId: 1
      }).then(function (data) {
        console.log(data);
      }).catch(function (err) {
        console.log(err);
      })
    }, */
    // 获取推荐女装
    getRecommendWomen () {
      this.$axios.get('/api/homePage/getRecommendWomen').then((data) => {
        // console.log(data);
        if (data.data.code === '200') {
          let arrList = []
          if (!data.data.data) {
            return false
          }
          for (let m of data.data.data) {
            let goods = {
              imgSrc: m.picUrl,
              hot: m.isRecommend,
              vip: m.isPlus,
              info: m.productName,
              progress: m.percent,
              sellerTaskId: m.sellerTaskId,
              msg: {
                pric: m.price,
                state: m.isMore,
                zhuan: m.extraGold,
                baina: '白拿'
              }
            }
            arrList.push(goods)
          }
          this.arrImg4 = arrList
          this.$nextTick(() => {
            this.$refs.scroll.refresh()
          })
        }
      }).catch((err) => {
        console.log(err)
      })
    },
    // 获取推荐男装
    getRecommendMan () {
      this.$axios.get('/api/homePage/getRecommendMan').then((data) => {
        if (data.data.code === '200') {
          let arrList = []
          if (!data.data.data) {
            return false
          }
          for (let m of data.data.data) {
            let goods = {
              imgSrc: m.picUrl,
              hot: m.isRecommend,
              vip: m.isPlus,
              info: m.productName,
              progress: m.percent,
              sellerTaskId: m.sellerTaskId,
              msg: {
                pric: m.price,
                state: m.isMore,
                zhuan: m.extraGold,
                baina: '白拿'
              }
            }
            arrList.push(goods)
          }
          this.arrImg5 = arrList
          this.$nextTick(() => {
            this.$refs.scroll.refresh()
          })
        }
      }).catch(function (err) {
        console.log(err)
      })
    },
    // 进入详情页面
    goDetail (item) {
      this.$router.push({ name: 'details', query: { sellerTaskId: item.sellerTaskId } })
    },
    // 进入筛选分类结果页面
    toClassPage (index) {
      this.$router.push({ name: 'nopay', query: { index: index } })
    }
  },
  mounted () {
    this.getBannerImg()
    this.getRecommendLottery()
    this.getRecommendSure()
    this.getQualityFree()
    // this.getRecommedProductByClass();
    this.getRecommendWomen()
    this.getRecommendMan()
  }
}
</script>
<style lang="stylus" rel="stylesheet/stylus" scoped>
.scrollContainer
  height 100%
  padding-bottom 9.6rem
  box-sizing border-box
.index_cont
  margin-bottom 5rem
  background rgba(0, 0, 0, 0.1)
.cont_top
  position relative
  .movement
    position absolute
    top 1.2rem
    left 1.2rem
    height 2.7rem
    max-width 22.8rem
    overflow hidden
    background rgba(0, 0, 0, 0.5)
    img
      float left
      width 2.7rem
      height 2.7rem
    .scrollFont
      float left
      .vux-marquee
        height 2.7rem
      li
        font-size 1rem
        color #fff
        line-height 2.7rem
  .top_btn
    display flex
    justify-content space-between
    padding 2rem
    background #fff
    li
      text-align center
      width 4.8rem
      img
        width 4rem
        height 4rem
        border-radius 50%
      span
        display block
        text-align center
        font-size 1.2rem
        white-space nowrap
        font-weight 300
        color #08090a
        line-height 3.2rem
.cont_show1
  margin-top 1.2rem
  background #fff
  h2
    color red
  .cont_show_title
    position relative
    overflow auto
    height 12rem
    color #fff
    background-size cover
    .m_title
      font-size 2rem
      color #fff
      letter-spacing 2px
      font-weight 600
      text-align center
      text-shadow 0 0.5px 2px rgba(8, 9, 10, 0.3)
      margin-top 3rem
      margin-bottom 1.5rem
    .m_all
      position absolute
      left 0
      right 0
      margin 0 auto
      letter-spacing 1px
      width 8rem
      color #fff
      text-align center
      border-top 2px solid rgba(255, 255, 255, 0.5)
      font-size 1.2rem
      padding-top 0.8rem
  h3
    font-size 1.6rem
    font-weight 300
    text-align center
    line-height 5.6rem
    color #08090a
    letter-spacing 0.1rem
  .cont_show_scroll
    height 26rem
    .scroll-content
      white-space nowrap
      .scroll_item
        display inline-block
        width 13rem
.cont_show2
  margin-top 1.2rem
  background #fff
  .cont_show_scroll
    .scroll_item
      display inline-block
      width 15.5rem
  h2
    font-size 1.6rem
    font-weight 300
    text-align center
    padding-top 2rem
    padding-bottom 1rem
    color #08090a
    letter-spacing 0.1rem
    span
      font-weight normal
      color #cc3d46
.cont_show3
  h2
    font-size 1.6rem
    font-weight 300
    text-align center
    line-height 5.6rem
    color #08090a
    letter-spacing 0.1rem
</style>
<style>
.scrollContainer .cont_show1 .img {
  width: 12.3rem;
  height: 12.3rem;
}

.scrollContainer .cont_show1 .cont_show_scroll .scroll-content .scroll_item {
  width: 12.3rem;
  margin-left: 0.8rem;
  margin-right: 0.8rem;
}

.scrollContainer .cont_show1 .wrap {
  padding: 0;
}

.scrollContainer .cont_show2 .img,
.scrollContainer .cont_show3 .img {
  width: 14.2rem;
  height: 14.2rem;
}

.scrollContainer .cont_show1 .cont_show_scroll {
  height: 20rem;
  padding-top: 1.6rem;
  padding-bottom: 1.6rem;
}

.scrollContainer .cont_show2 .wrap,
.scrollContainer .cont_show2 .wrap {
  padding: 0;
}

.scrollContainer .cont_show2 .cont_show_scroll .scroll_item,
.scrollContainer .cont_show3 .cont_show_scroll .scroll_item {
  width: 14.2rem;
  margin: 2rem 0 2rem 1.2rem;
}

.vux-swiper-desc {
  display: none;
}
</style>

