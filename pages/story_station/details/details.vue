<template>
	<view class="details">
		<view class="img"></view>
		<view class="name">玩家名称</view>
		<view class="desc">玩家故事文案玩家故事文案玩家故事文案玩家故事文案玩家故事文案玩家故事文案玩家故事文案玩家故事文案玩家故事文案玩家故事文案玩家故事文案玩家故事文案玩家故事文案玩家故事文案</view>
		<view class="buttom">
			<text class="x">1724</text>
			<text class="zc" @tap="tourl">制作同款</text>
		</view>
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
					url:"../make/make"
				})
			}
		}
	}
</script>

<style lang="scss">
.details{
	padding: 20upx 40upx 120upx;
	.img{
		width: 100%;
		height: 800upx;
		background: #333;
	}
	.name{
		padding: 20upx 0;
		font-size: 32upx;
	}
	.desc{
		font-size: 28upx;
		line-height: 36upx;
		color: #666;
	}
	.buttom{
		position: fixed;
		bottom: 0;
		left: 0;
		width: 100%;
		height: 100upx;
		line-height: 100upx;
		text-align: center;
		display: flex;
		border-top: 1upx solid #aaa;
		text{
			flex: 1;
			&.zc{
				background: #aaa;
			}
		}
	}
}
</style>
