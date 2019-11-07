<template>
	<swiper  class="banner">
    <!-- slides -->
    <swiper-slide>I'm Slide 1</swiper-slide>
    <swiper-slide>I'm Slide 2</swiper-slide>
    <swiper-slide>I'm Slide 3</swiper-slide>
    <swiper-slide>I'm Slide 4</swiper-slide>
    <swiper-slide>I'm Slide 5</swiper-slide>
    <swiper-slide>I'm Slide 6</swiper-slide>
    <swiper-slide>I'm Slide 7</swiper-slide>
    <!-- Optional controls -->
    <div class="swiper-pagination"  slot="pagination"></div>
    
  </swiper>
</template>
<script>
	export default {
		name: 'index-slider',
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
		background: blue
</style>