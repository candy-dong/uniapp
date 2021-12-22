<template>
	<view>
		<!-- <view><text>唱歌跳舞打篮球</text></view>
		<view><text selectable space="ensp">唱歌 跳舞   打篮球</text></view>
		<view><text space="emsp">唱歌跳舞   打篮球</text></view>
		<view><text space="nbsp" style="font-size: 30px;">唱歌跳舞   打篮球</text></view>
		<view><text>&amp;</text></view> -->
		<view class="box2" hover-class="box2-active">
			<view :hover-start-time="2000" :hover-stay-time="2000" class="box" hover-class="box-active" hover-stop-propagation></view>
		</view>
		<button>按钮</button>
		<button size="mini">按钮</button>
		<button type="primary">按钮</button>
		<button type="primary" plain>按钮</button>
		<button type="primary" disabled>按钮</button>
		<button loading></button>
	</view>
</template>

<script>
</script>

<style>
	.box {
		width: 100px;
		height: 100px;
		background-color: green;
	}
	.box-active {
		background-color: red;
	}
	.box2 {
		width: 200px;
		height: 200px;
		background-color: #007AFF;
	}
	.box2-active {
		background-color: pink;
	}
</style>
