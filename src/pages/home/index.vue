<template>
<div id="" class="header">
<index-header></index-header>
<slider></slider>
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
		methods: {
			getIndexData () {
//			   axios.get('/api/index.json')
//			  .then(this.handleDataSucc.bind(this)).catch(this.handleDataError.bind(this))
			},
			handleDataSucc (response) {
				console.log(response)
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