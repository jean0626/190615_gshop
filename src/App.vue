<template>
  <div id="app">
	  
		<router-view></router-view>
		<!-- <FooterGuide/> -->
		<FooterGuide v-show="$route.meta.showFooter" />
  </div>
</template>

<script>
	import FooterGuide from './components/FooterGuide/FooterGuide.vue'
	// import FooterGuide from './components/FooterGuide/FooterGuide.vue'
	  export default {
	  components: {
	    FooterGuide
	  }
	}
</script>

<style lang="stylus" rel="stylesheet/stylus">
	#app
		top-border-1px(#e4e4e4)
		width 100%
		background-color #fff
</style>
