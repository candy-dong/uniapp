<template>
	<view class="content">
		<!-- <image class="logo" src="/static/logo.png"></image>
		<view class="text-area">
			<text class="title">{{title}}</text>
		</view> -->
		<test  :title="title" @myEven="getNum"></test>
		这是子组件数值{{num}}
		<test-a></test-a>
		<test-b></test-b>
	</view>
</template>

<script>
	import test from "../../components/test.vue"
	import testA from "../../components/a.vue"
	import testB from "../../components/b.vue"
	export default {
		data() {
			return {
				title: 'Hello',
				num: 0
			}
		},
		components:{
			test,
			"test-a":testA,
			"test-b":testB
		},
		onLoad(options) {
			console.log('页面加载了',options)
		},
		onShow() {
			console.log('页面显示了')
		},
		onReady() {
			console.log('页面初次渲染完成')
		},
		onHide() {
			console.log('页面隐藏了')
		},
		methods: {
			getNum(num){
				console.log(num)
				this.num = num
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
