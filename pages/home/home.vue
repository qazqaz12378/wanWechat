<template>
	<view>
		<u-swiper :list="list" name="imagePath" height="35px" img-mode="aspectFit" @click="click"></u-swiper>
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
			click(index) {
				var url =this.list[index]['url']
				uni.navigateTo({
					url:"../webview/webview?url="+url
				})
			}
		}
	}
</script>

<style>

</style>
