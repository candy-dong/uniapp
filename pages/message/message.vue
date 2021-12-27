<template>
	<view>
		<button type="primary" @click="chooseImg">上传图片</button>
		<image v-for="item in imgArr" :src="item" @click="previewImg(item)"></image>
	</view>
</template>

<script>
	export default{
		data() {
			return{
				imgArr: []
			}
		},
		methods:{
			chooseImg(){
				uni.chooseImage({
					count: 5,
					success: res=>{
						this.imgArr = res.tempFilePaths
					}
				})
			},
			previewImg(current) {
				console.log(current)
				uni.previewImage({
					current,
					urls: this.imgArr,
					indicator: 'number'
				})
			}
		}
	}
</script>

<style>
</style>
