<template>
	<view class="">
		<button type="default" @click="btn">这是a组件 修改b的数据</button>
	</view>
</template>

<script>
	export default{
		data(){
			return{
				
			}
		},
		methods:{
			btn(){
				uni.$emit('myEvent',10)
			}
		}
	}
</script>

<style>
</style>
