<template>
	<view>
		<view>这是列表页</view>
		<view v-for="item in list">{{item}}</view>
		<button type="default" @click="pullDown">下拉刷新</button>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				list: ['前端','java','大数据','UI','测试']
			}
		},
		onPullDownRefresh(){
			console.log('触发了下拉刷新')
			this.list = ['java','大数据','UI','测试','前端']
			setTimeout(function () {
				uni.stopPullDownRefresh();
			}, 2000);
		},
		methods: {
			pullDown() {
				uni.startPullDownRefresh()
			}
		}
	}
</script>

<style>
</style>
