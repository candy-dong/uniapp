<template>
	<view>
		<view>
			这是A组件
			<button @click="addNum">修改B组件的数据</button>
		 </view>
	</view>
</template>

<script>
	export default {
		name:"a",
		data() {
			return {
				
			};
		},
		methods:{
			addNum(){
				uni.$emit('updateNum',10)
			}
		}
	}
</script>

<style>

</style>
