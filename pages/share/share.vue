<template>
	<view class="share">
		<view class="img"></view>
		<view class="btn">分享给朋友</view>
		<view class="btn">保存图片</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			};
		}
	}
</script>

<style lang="scss">
.share{
	padding: 30upx 50upx;
	.img{
		height: 800upx;
		background: #aaa;
	}
	.btn{
		width: 100%;
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
