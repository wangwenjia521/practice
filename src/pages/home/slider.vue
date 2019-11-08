<template>
	<swiper  class="banner index-banner" :options="swiperOption">
    <!-- slides -->
    <swiper-slide v-for="item in sliders" :key="item.id">
    	<img :src="item.imgUrl" alt="" class="banner-img" />
    </swiper-slide>
   		
    <!-- Optional controls -->
    <div class="swiper-pagination"  slot="pagination"></div>
  </swiper>
</template>
<script>
	export default {
		name: 'index-slider',
		 data() {
	      return {
	        swiperOption: {
	         pagination: '.swiper-pagination'
	        }
	      }
	   },
		props: {
			sliders: Array
		},
		mounted () {
			
		}
	}
</script>

<style scoped lang="stylus">
	@import  '../../assets/styles/common/varibles.styl'
	.banner
		height: 0
		overflow: hidden
		padding-bottom: 31.25%
		.banner-img
			width: 100%
</style>
<style type="text/css" lang="stylus">
.index-banner
	.swiper-pagination-bullet
		background:#fff
</style>