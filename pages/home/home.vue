<template>
	<view>
		<u-swiper :list="list" name="imagePath" height="35px" img-mode="aspectFit"></u-swiper>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				list :[
					
				],
				
			}
		},
		onLoad:function(){
			
			uni.request({
				url:"https://www.wanandroid.com/banner/json",
				method: 'GET',
				data: {},
				success: res => {
				   this.list = res.data.data
				},
				fail: () => {},
				complete: () => {}
			});
		},
		methods: {
			
		}
	}
</script>

<style>

</style>
