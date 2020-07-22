<template>
	<view class="">
		<button type="primary" @click="choose">上传图片</button>
		<view class="">
				<image v-for="(item,index) in data" :key=index :src="item" mode="" @click="click1(item)"></image>
		</view>
	</view>
</template>

<script>
	export default{
		data(){
			return{
				data:[]
			}
		},
		methods:{
			choose(){
				uni.chooseImage({
					count:2,
					success:res => {
						this.data = res.tempFilePaths  //将文件的路径存在 data中循环遍历
					}
				})
			},
			click1(current){
				console.log(current);
				console.log(this.data)
				uni.previewImage({
					current,
					urls:this.data
				})
			}
		}
	}
	
</script>

<style>
	
</style>
