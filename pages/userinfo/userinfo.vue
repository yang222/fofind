<template>
	<view class="Story">
		<view class="nav">
			<text class="act">我的专属海报</text>
			<text>我赞的海报</text>
		</view>
		<view class="list">
			<view class="item" v-for="(item,index) in list" :key="index" @tap="tourl">
				<view class="img"></view>
				<view class="info">
					<text class="name">1234</text>
					<text class="num">删除</text>
				</view>
				<!-- <view class="desc">这是简介</view> -->
			</view>
		
		</view>
		<!-- <view class="user_dz" @tap="toMake()">
			<text>个人</text>
			<text>定制</text>
		</view>
		<view class="user_info">
			<text>个人</text>
			<text>中心</text>
		</view> -->
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: '这是玩家故事站页面',
				list:[1,2,3,4,5,6,7,8,9,10]
			}
		},
		onLoad() {

		},
		methods: {
			tourl(){
				uni.navigateTo({
					url:"../story_station/details/details"
				})
			},
			toMake(){
				uni.navigateTo({
					url:"make/make"
				})
			}
		}
	}
</script>

<style lang="scss">
.Story{
	.nav{
		position: fixed;
		top: 0;
		left: 0;
		width: 100%;
		height: 70upx;
		line-height: 70upx;
		padding: 0 20upx;
		font-size: 36upx;
		background: #fff;
		text{
			display: inline-block;
			padding: 0 30upx;
			height: 70upx;
			box-sizing: border-box;
			&.act{
				font-size: 42upx;
				color: #8A6DE9;
				border-bottom: 8upx solid #8A6DE9;
			}
		}
	}
	.list{
		padding: 90upx 20upx 30upx;
		font-size: 0;
		.item{
			display: inline-block;
			width: 48%;
			margin-bottom: 20upx;
			.img{
				width: 100%;
				height: 400upx;
				background: #666;
			}
			&:nth-child(2n+1){
				margin-right: 3%;
			}
			.info{
				font-size: 32upx;
				display: flex;
				line-height: 60upx;
				.name{
					flex: 1;
				}
				.num{
					width: 150upx;
					text-align: right;
				}
			}
			.desc{
				font-size: 24upx;
				color: #999;
			}
		}
	}
	.user_dz,.user_info{
		position: fixed;
		bottom: 120upx;
		width: 100upx;
		box-sizing: border-box;
		padding: 10upx 0;
		height: 100upx;
		line-height: 40upx;
		border-radius: 50%;
		background: #333;
		color: #fff;
		right: 10upx;
		font-size: 24upx;
		text{
			text-align: center;
			display: block;
		}
	}
	.user_info{
		bottom: 10upx;
	}
}
</style>
