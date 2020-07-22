<template>
	<view class="">
		<button type="default">
			这是b组件 {{num}}
		</button>
	</view>
</template>

<script>
	export default{
		data(){
			return{
				num:0
			}
		},
		created(){
			uni.$on('myEvent',(res)=>{
				this.num += res
			})
		}
	}
</script>

<style>
</style>
