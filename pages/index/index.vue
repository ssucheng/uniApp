<template>
	<view class="content">
		<image class="logo" src="/static/logo.png"></image>
		<view class="text-area">
			<text class="title">{{title}}</text>
			<!-- <text>{{name}}</text> -->
			<sc-text title='sucheng'></sc-text>
			<sc-text :title='msg'></sc-text>
			
		</view>
		
		<view class="">
			<sc-text1 @myEvent="getSonData"></sc-text1>
		</view>
		<!-- 兄弟组件传值 -->
		<view class="">
			<sc-a></sc-a>
			<sc-b></sc-b>
		</view>
	</view>
</template>

<script>
	import text from '@/components/text.vue'
	import text1 from '@/components/text1.vue'
	import a from '@/components/a.vue'
	import b from '@/components/b.vue'
	
	export default {
	components:{
		scText:text,
		scText1:text1,
		scA:a,
		scB:b
	},
		data() {
			return {
				title: 'Hello',
				msg:'hello'
				
			}
		},
		onLoad(options) {
			console.log(options)
			//options 是可以接受到其他页面传递的参数  用onlaod的函数接受
			console.log('页面加载了',options)
		},
		onShow(){
			console.log('页面显示了');
		},
		onReady(){
			console.log('页面初次渲染完成了');
			
		},
		methods: {
			getSonData(res){
				console.log(res)
			}
		}
	}
</script>

<style>
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}

	.logo {
		height: 200rpx;
		width: 200rpx;
		margin-top: 200rpx;
		margin-left: auto;
		margin-right: auto;
		margin-bottom: 50rpx;
	}

	.text-area {
		display: flex;
		justify-content: center;
	}

	.title {
		font-size: 36rpx;
		color: #8f8f94;
	}
</style>
