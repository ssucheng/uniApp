<template>
	<view class="">
		<button type="primary" @click="btn">我是子组件</button>
	</view>
</template>

<script>
	export default{
		props:{
			msg:{
				type:String,
				value:''
			}
		},
		data(){
			return{
				data:'子传值给父'
			}
		},
		methods:{
			btn(){
				this.$emit('myEvent',this.data)
			}
		}
	}
</script>

<style>
</style>
