<template>
	<view>
		<view>这是列表页</view>
		<!-- <view class="box-item" v-for="item in list">{{item}}</view> -->
		<!-- <button type="default" @click="pullDown">下拉刷新</button> -->
		<button type="primary" @click="setStorage">存储数据</button>
		<button type="primary" @click="getStorage">获取数据</button>
		<button type="primary" @click="removeId">移除数据</button>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				list: ['前端','java','大数据','UI','测试','UI','测试','前端','java','大数据','UI','测试','前端']
			}
		},
		onPullDownRefresh(){
			console.log('触发了下拉刷新')
			this.list = ['java','大数据','UI','测试','前端','java','大数据','UI','测试','前端']
			setTimeout(function () {
				uni.stopPullDownRefresh();
			}, 2000);
		},
		onReachBottom() {
			console.log('页面触底了')
			this.list = [...this.list,...['java','大数据','UI','测试','前端','java','大数据']]
		},
		methods: {
			pullDown() {
				uni.startPullDownRefresh()
			},
			setStorage(){
				// uni.setStorage({
				// 	key: 'id',
				// 	data: 80,
				// 	success() {
				// 		console.log('存储成功')
				// 	}
				// })
				uni.setStorageSync('id',100);
			},
			getStorage() {
				// uni.getStorage({
				// 	key:'id',
				// 	success(res){
				// 		console.log('获取成功',res.data)
				// 	}
				// })
				const res = uni.getStorageSync('id')
				console.log(res)
			},
			removeId() {
				// uni.removeStorage({
				// 	key: 'id',
				// 	success() {
				// 		console.log('移除成功')
				// 	}
				// })
				uni.removeStorageSync('id')
			}
		}
	}
</script>

<style>
	.box-item {
		width: 100px;
		line-height: 100px;
	}
</style>
