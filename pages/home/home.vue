<template>
	<view>
		<view>数据绑定的学习</view>
		<view>{{msg}}</view>
		<view>{{'你好' + '世界'}}</view>
		<view>{{1+1}}</view>
		<view>{{flag?'这是反话，我是假的':'这是反话，我是真的'}}</view>
	</view>
 </template>

<script>
	export default {
		data() {
			return {
				msg: 'hello',
				flag: true
			}
		}
	}
</script>

<style>
</style>
