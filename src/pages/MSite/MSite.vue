<template>
	<div class="on">
	  <section class="msite">
	    <!--首页头部-->
	    <!-- <header class="header">
	      <span class="header_search">
	        <i class="iconfont icon-sousuo"></i>
	      </span>
	      <span class="header_title">
	        <span class="header_title_text ellipsis">昌平区北七家宏福科技园(337省道北)</span>
	      </span>
	      <span class="header_login">
	        <span class="header_login_text">登录|注册</span>
	      </span>
	    </header> -->
			<HeaderTop title="昌平区北七家宏福科技园(337省道北)">
				<span class="header_search" slot="left">
				  <i class="iconfont icon-sousuo"></i>
				</span>
				<span class="header_login" slot="right">
				  <span class="header_login_text">登录|注册</span>
				</span>
			</HeaderTop>
			<!-- <HeaderTop title="我的"/> -->

        <!--首页导航-->
        <nav class="msite_nav">
          <div class="swiper-container">
            <div class="swiper-wrapper">
              <div class="swiper-slide">
                <a href="javascript:" class="link_to_food">
                  <div class="food_container">
                    <img src="./images/nav/1.jpg">
                  </div>
                  <span>甜品饮品</span>
                </a>
                <a href="javascript:" class="link_to_food">
                  <div class="food_container">
                    <img src="./images/nav/2.jpg">
                  </div>
                  <span>商超便利</span>
                </a>
                <a href="javascript:" class="link_to_food">
                  <div class="food_container">
                    <img src="./images/nav/3.jpg">
                  </div>
                  <span>美食</span>
                </a>
                <a href="javascript:" class="link_to_food">
                  <div class="food_container">
                    <img src="./images/nav/4.jpg">
                  </div>
                  <span>简餐</span>
                </a>
                <a href="javascript:" class="link_to_food">
                  <div class="food_container">
                    <img src="./images/nav/5.jpg">
                  </div>
                  <span>新店特惠</span>
                </a>
                <a href="javascript:" class="link_to_food">
                  <div class="food_container">
                    <img src="./images/nav/6.jpg">
                  </div>
                  <span>准时达</span>
                </a>
                <a href="javascript:" class="link_to_food">
                  <div class="food_container">
                    <img src="./images/nav/7.jpg">
                  </div>
                  <span>预订早餐</span>
                </a>
                <a href="javascript:" class="link_to_food">
                  <div class="food_container">
                    <img src="./images/nav/8.jpg">
                  </div>
                  <span>土豪推荐</span>
                </a>
              </div>
              <div class="swiper-slide">
                <a href="javascript:" class="link_to_food">
                  <div class="food_container">
                    <img src="./images/nav/9.jpg">
                  </div>
                  <span>甜品饮品</span>
                </a>
                <a href="javascript:" class="link_to_food">
                  <div class="food_container">
                    <img src="./images/nav/10.jpg">
                  </div>
                  <span>商超便利</span>
                </a>
                <a href="javascript:" class="link_to_food">
                  <div class="food_container">
                    <img src="./images/nav/11.jpg">
                  </div>
                  <span>美食</span>
                </a>
                <a href="javascript:" class="link_to_food">
                  <div class="food_container">
                    <img src="./images/nav/12.jpg">
                  </div>
                  <span>简餐</span>
                </a>
                <a href="javascript:" class="link_to_food">
                  <div class="food_container">
                    <img src="./images/nav/13.jpg">
                  </div>
                  <span>新店特惠</span>
                </a>
                <a href="javascript:" class="link_to_food">
                  <div class="food_container">
                    <img src="./images/nav/14.jpg">
                  </div>
                  <span>准时达</span>
                </a>
                <a href="javascript:" class="link_to_food">
                  <div class="food_container">
                    <img src="./images/nav/1.jpg">
                  </div>
                  <span>预订早餐</span>
                </a>
                <a href="javascript:" class="link_to_food">
                  <div class="food_container">
                    <img src="./images/nav/2.jpg">
                  </div>
                  <span>土豪推荐</span>
                </a>
              </div>
            </div>
            <!-- Add Pagination -->
            <div class="swiper-pagination"></div>
          </div>
        </nav>
				<!-- ////////////aaaaaaaaaaaaaa -->
				 <ShopList></ShopList>
				<!-- ////////////aaaaaaaaaaaaaa -->

      </section>
    </div>	
</template>

<script>
	import HeaderTop from '../../components/HeaderTop/HeaderTop.vue'
	import Swiper from 'swiper'
	import ShopList from '../../components/ShopList/ShopList.vue'
	import 'swiper/dist/css/swiper.min.css'
	import {mapState} from 'vuex'
	export default {
		mounted() {
			new Swiper('.swiper-container',{
				loop:true,
				pagination:{
					el:'.swiper-pagination'
				}
				
			})
		},
		components:{
			HeaderTop,
			ShopList
		},
		
		
    data () {
      return {
        baseImageUrl: 'https://fuss10.elemecdn.com'
      }
    },
//     mounted () {
// 
//       // this.$store.dispatch('getCategorys')
//       // this.$store.dispatch('getShops')
//     },
		computed: {
		  ...mapState(['address', 'categorys', 'userInfo']),
		
		  /*
		  根据categorys一维数组生成一个2维数组
		  小数组中的元素个数最大是8
		   */
		  categorysArr () {
		    const {categorys} = this
		    // 准备空的2维数组
		    const arr = []
		    // 准备一个小数组(最大长度为8)
		    let minArr = []
		    // 遍历categorys
		    categorys.forEach(c => {
		      // 如果当前小数组已经满了, 创建一个新的
		      if(minArr.length===8) {
		        minArr = []
		      }
		      // 如果minArr是空的, 将小数组保存到大数组中
		      if(minArr.length===0) {
		        arr.push(minArr)
		      }
		      // 将当前分类保存到小数组中
		      minArr.push(c)
		    })
		
		    return arr
		  },
		
			
		}
 }
	
	
</script>

	
<style lang="stylus" rel="stylesheet/stylus">
  @import "../../common/stylus/mixins.styl"	
	.header
	  background-color #02a774
	  position fixed
	  z-index 100
	  left 0
	  top 0
	  width 100%
	  height 45px
	  .header_search
	    position absolute
	    left 15px
	    top 50%
	    transform translateY(-50%)
	    width 10%
	    height 50%
	    .icon-sousuo
	      font-size 25px
	      color #fff
	  .header_title
	    position absolute
	    top 50%
	    left 50%
	    transform translate(-50%, -50%)
	    width 50%
	    color #fff
	    text-align center
	    .header_title_text
	      font-size 20px
	      color #fff
	      display block
	  .header_login
	    font-size 14px
	    color #fff
	    position absolute
	    right 15px
	    top 50%
	    transform translateY(-50%)
	    .header_login_text
	      color #fff
	.msite_nav
	  bottom-border-1px(#e4e4e4)
	  margin-top 45px
	  height 200px
	  background #fff
	  .swiper-container
	    width 100%
	    height 100%
	    .swiper-wrapper
	      width 100%
	      height 100%
	      .swiper-slide
	        display flex
	        justify-content center
	        align-items flex-start
	        flex-wrap wrap
	        .link_to_food
	          width 25%
	          .food_container
	            display block
	            width 100%
	            text-align center
	            padding-bottom 10px
	            font-size 0
	            img
	              display inline-block
	              width 50px
	              height 50px
	          span
	            display block
	            width 100%
	            text-align center
	            font-size 13px
	            color #666
	    .swiper-pagination
	      >span.swiper-pagination-bullet-active
	        background #02a774
	.msite_shop_list
	  top-border-1px(#e4e4e4)
	  margin-top 10px
	  background #fff
	  .shop_header
	    padding 10px 10px 0
	    .shop_icon
	      margin-left 5px
	      color #999
	    .shop_header_title
	      color #999
	      font-size 14px
	      line-height 20px
</style>
