<template>
	<view class="">
		<!-- 跳转tabbar页面必须添加 open-type="switchTab" -->
		<!-- 组件跳转 -->
		<navigator url="/pages/index/index" open-type="switchTab">
			<button type="default" @click="btn">组件跳转到index页面</button>
		</navigator>
		<button type="default" @click="btn1">api跳转</button>
		<button type="default" @click="btn2">tabbar跳转</button>
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
					console.log(1);
				},
				btn1(){
					uni.navigateTo({
						url:'/pages/list/list' //跳转普通页面
					})
				},
				btn2(){
					uni.switchTab({
						url:'/pages/index/index' //跳转tabbar页面
					})
				}
			}
		
	}
</script>

<style>
</style>
