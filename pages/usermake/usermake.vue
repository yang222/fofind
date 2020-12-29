<template>
	<view class="userMake">
		<view class="img">
			<image src="../../static/tit.png" class="share-img"  mode="aspectFit"></image>
		</view>
		<view class="btn" @tap="tourl(1)">立即制作</view>
		<view class="btn" @tap="tourl(2)">容我想想</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			};
		},
		methods:{
			tourl(type){
				
				if(type ==1){
					uni.navigateTo({
						url:"../story_station/make/make"
					})
				}else{
					uni.switchTab({
						url:"../index/index"
					})
				}
			}
		}
	}
</script>

<style lang="scss">
.userMake{
	padding: 60upx 0 40upx;
	.img{
		width: 80%;
		margin: 0 auto;
		margin-bottom: 60upx;
		text-align: center;
		.share-img{
			height:500upx;
		}
	}
	.btn{
		width: 80%;
		margin: 0 auto;
		margin-top: 60upx;
		color: red;
		height: 100upx;
		line-height: 100upx;
		text-align: center;
		line-height: 100upx;
		background: #8A6DE9;
		border-radius: 5upx;
	}
}
</style>
