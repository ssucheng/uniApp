<template>
	<view class="">
		<button type="default" @click="btn">设置storage</button>
		<button type="default" @click="btn1">获取storage</button>
		<button type="default" @click="btn3">t同步设置storage</button>
		<button type="default" @click="btn4">同步获取storage</button>
		<button type="default" @click="btn5">异步删除storage</button>
		<button type="default" @click="btn6">同步删除storage</button>
		<button type="default">{{id}}</button>
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
				data:["前端","后端","html","java"],
				id:''
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
			// this.data = [...this.data,...this.data]
			this.get()
		},
		methods:{
			get(){
				uni.request({
					url:'http://localhost:8082/api/getlunbo',
					success:res => {
						console.log(res)
						
					}
				})
			},
			btn(){
				let that = this
				uni.setStorage({  //异步的形式
					key:'id',
					data:10,
					success(res){
						console.log(res)
						// console.log(that);
					}
				})
			},
			btn1(){
				uni.getStorage({  //异步的形式
					key:'id',
					success: res => {
						console.log(res)
						console.log(this)//this 指向vue实例
						this.id = res.data
					}
				})
			},
			btn3(){
				uni.setStorageSync('id',100)
				console.log('同步设置成功');
			},
			btn4(){
			const id =	uni.getStorageSync('id')
			console.log('同步获取成功');
			this.id = id
			
			},
			btn5(){
				let that = this
				uni.removeStorage({
					key:'id',
					success:function(){
						console.log('删除成功')
						that.id = ''
					}
				})
				
			},
			btn6(){
				uni.removeStorageSync('id')
				console.log('同步删除成功');
				this.id = ''
			}
		}
	}
</script>

<style lang="scss">
	.box{
		height: 300px;
		line-height: 300px;
	}
</style>
