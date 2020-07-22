<template>
	<view class="">
		我是text 组件
		我{{title}}是父组件传进来的值
	</view>
</template>
<script>
	export default{
		props:['title'],
		data(){
			return{
				
			}
		},
		
	}
</script>

<style>
</style>
