<template>
	<view>
		<view>这是test组件</view>
		<view>这是父组件传过来的数据{{title}}</view>
		<button @click="sendNum">子传父</button>
	</view>
</template>

<script>
	export default{
		data(){
			return{
				num: 3
			}
		},
		props:['title'],
		methods:{
			sendNum(){
				console.log('给父组件传值')
				this.$emit('myEven',this.num)
			}
		}
	}
</script>

<style>
</style>
