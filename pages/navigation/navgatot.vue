<template>
	<view class="">
		<navigator url="/pages/index/index" open-type="switchTab">
			<button type="default" @click="btn">跳转到index页面</button>
		</navigator>
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
				}
			}
		
	}
</script>

<style>
</style>
