<template>
<div id="" class="header">
<index-header></index-header>
<slider :sliders = "sliders"></slider>
</div>
</template>

<script>
	import IndexHeader from './header'
	import Slider from './slider'
	import axios from 'axios'
	export default {
		name: 'index',
		components: {
			IndexHeader,
			Slider
		},
		data () {
			return {
				sliders: []
			}
		},
		methods: {
			getIndexData () {
			   axios.get('/api/index.json')
			  .then(this.handleDataSucc.bind(this)).catch(this.handleDataError.bind(this))
			},
			handleDataSucc (res) {
				res = res ? res.data: null;
				if(res && res.ret && res.data) {
					 this.sliders = res.data.silders;
				}
			},
			handleDataError (err) {
				console.log(err)
			}
			
		},
		mounted () {
			this.getIndexData()
		}
	}
</script>

<style scoped>
	
</style>