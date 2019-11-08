<template>
	<swiper  class="icons index-icons" :options="swiperOption">
    <!-- slides -->
    <swiper-slide v-for="(page, index) in pages" :key="index">
    	<div>
    		<div v-for="item in page" :key="item.id">
    			<img :src="item.imgUrl" alt="" />
    		</div>
    	</div>	
    </swiper-slide>
	
    <!-- Optional controls -->
    <div class="swiper-pagination"  slot="pagination"></div>
  </swiper>
</template>
<script>
	export default {
		name: 'icons',
		 data() {
	      return {
	        swiperOption: {
	         pagination: '.swiper-pagination'
	        }
	      }
	   },
		props: {
			icons: Array
		},
		computed :{
			pages () {
				const pages = []
				this.icons.forEach((value ,index) => {
					const page = Math.floor( index / 8 )
//					console.log(page)
					if(!pages[page]) {
						pages[page] = []
					}
					
					pages[page].push(value)
				})
				return pages
			}
		},
//		mounted () {
//			setTimeout(() => {
//				console.log(this.pages)
//			}, 2000)
//		}
	}
</script>

<style scoped lang="stylus">
	@import  '../../assets/styles/common/varibles.styl'
	
</style>
<style type="text/css" lang="stylus">
@import  '../../assets/styles/common/varibles.styl'
	
</style>