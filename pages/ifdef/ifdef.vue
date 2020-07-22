<template>
	<view class="">
		<!-- #ifdef H5 -->
		<view class="box1">
			h5页面会显示
		</view>
		<!-- #endif -->
		<!-- #ifdef  MP-WEIXIN -->
		<view class="box2">
			微信页面会显示
		</view>
		<!-- #endif -->
	</view>
</template>

<script>
	export default{
		onLoad(){
			// #ifdef H5
				console.log('h5');
			// #endif
			// #ifdef MP-WEIXIN
				console.log('微信')
			// #endif
		}
	}
</script>

<style>
	/* #ifdef H5 */
		view{
			color: pink;
		}
	/* #endif */
	/* #ifdef MP-WEIXIN */
		view{
			color: red;
		}
	/* #endif */
</style>
