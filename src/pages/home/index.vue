<template>
<div id="" class="header">
<index-header></index-header>
<slider :sliders = "sliders"></slider>
<icons :icons="icons"></icons>
</div>
</template>

<script>
	import IndexHeader from './header'
	import Slider from './slider'
	import Icons from './icons'
	import axios from 'axios'
	import {mapState } from 'vuex'
	export default {
		name: 'index',
		components: {
			IndexHeader,
			Slider,
			Icons
		},
		data () {
			return {
				sliders: [],
				icons: []
			}
		},
		computed: {
			...mapState(['city'])
		},
		methods: {
			getIndexData () {
			   axios.get('/api/index.json?city=' + this.city)
			  .then(this.handleDataSucc.bind(this)).catch(this.handleDataError.bind(this))
			},
			handleDataSucc (res) {
				res = res ? res.data: null;
				if(res && res.ret && res.data) {
					res.data.sliders && (this.sliders = res.data.sliders)
					res.data.icons && (this.icons = res.data.icons)
				} else {
					this.handleDataErr()
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