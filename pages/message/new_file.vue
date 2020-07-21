<template>
	<view class="">
		<view>{{text}}
		
		<text selectable="true">
			我是可选文本
		</text>
		
		</view>
		<!-- 显示连续空格的方式 -->
		<view class="">
			<!-- 中文一半的大小 -->
			<text space="ensp">
				来了 老弟
			</text>
			
		</view>
		<view class="">
			 <!-- 中文一个大小 -->
			<text space="emsp">
				来了 老弟
			</text>
			
		</view>
		<view class="">
			<!-- 根据字体的大小变换大小 -->
			<text space="nbsp">
				来了 老弟
			</text>
		</view>
		<view>
			<!-- &lt;h5端可以渲染  微信端报错 -->
			<text decode = "true"> &nbsp;  &gt; &amp; &apos; &ensp; &emsp; </text>
		</view>
	</view>
	
</template>
	
<script>
	export default {
		data(){
			return {
				text:'hello word'
			}
		}
	}
</script>

<style>
</style>
