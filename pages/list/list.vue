<template>
	<view class="">
		
		<text>这是列表页</text>
		<view v-for="(item,index) in data" :key=index class="box">
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
		},
		onReachBottom(){//页面触底的函数
			console.log('页面触底了');
			this.data = [...this.data,...this.data]
		}
	}
</script>

<style lang="scss">
	.box{
		height: 300px;
		line-height: 300px;
	}
</style>
