<template>
	<view class="">{{home}}</view>
</template>

<script>
	export default {
		data() {
			return {
				home: 'home'
			}
		},
		onLoad(e) {
			uni.setNavigationBarTitle({
				title: e.name
			})
			this.home = `home_${e.id}`
		},
		methods: {
			name() {
				
			}
		},
	}
</script>

<style>
</style>
