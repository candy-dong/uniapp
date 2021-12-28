<template>
	<view>
		<view>导航跳转的学习</view>
		<!-- 声明式导航 -->
		<navigator url="../detail/detail">跳转至详情页</navigator>
		<navigator url="../detail/detail?id=80&age=19">跳转至详情页</navigator>
		<!-- open-type是switchTab不可传参 -->
		<navigator url="../message/message" open-type="switchTab">跳转至信息页</navigator>
		<navigator url="../detail/detail" open-type="redirect">redirect跳转至详情页</navigator>
		<!-- 编程导航 -->
		<button @click="goDetail">跳转至详情页</button>
		<button @click="goMessage">跳转至信息页</button>
		<button @click="redirectDetail">跳转至详情页并关闭当前页面</button>
	</view>
</template>

<script>
	export default {
		onLoad() {
			console.log('导航页面卸载了')
		},
		methods:{
			goDetail(){
				uni.navigateTo({
					url: '../detail/detail?id=5&age=19'
				})
			},
			goMessage(){
				uni.switchTab({//不可传参
					url: '/pages/message/message?id=5'
				})
			},
			redirectDetail(){
				uni.redirectTo({
					url: '../detail/detail?id=5'
				})
			},
			
		}
	}
	
</script>

<style>
</style>
