<template>
	<view class="make">
		<view class="img">
			<image src="../../../static/make.png" class="imgCover" mode="aspectFit"></image>
		</view>
		<view class="btn" @tap="tourl">定制完成</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			};
		},
		methods:{
			tourl(){
				uni.navigateTo({
					url:"../../share/share"
				})
			}
		}
	}
</script>

<style lang="scss">
.make{
	.img{
		height: 1200upx;
		padding-bottom: 120upx;
		.imgCover{
			height: 100%;
			width: 100%;
		}
	}
	.btn{
		position: fixed;
		bottom: 0;
		left: 0;
		width: 100%;
		height: 100upx;
		line-height: 100upx;
		text-align: center;
		background: #aaa;
		border-top: 1upx solid #aaa;
		
	}
}
</style>
