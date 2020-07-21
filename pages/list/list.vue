<template>
	<view class="">
		
		<text>这是列表页</text>
		<view v-for="(item,index) in data" :key=index>
			{{item}}
		</view>
	</view>
	
</template>

<script>
	export default{
		data(){
			return {
				data:["前端","后端","html","java"]
			}
		},
		onPullDownRefresh(){
			console.log('触发了页面刷新')
			this.data = ["11","2222","3333"]
			//解除刷新
			uni.stopPullDownRefresh()
		}
	}
</script>

<style>
</style>
