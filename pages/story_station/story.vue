<template>
	<view class="Story">
		<view class="nav">
			<text class="act">最新</text>
			<text>热门</text>
		</view>
		<view class="list">
			<view class="item" v-for="(item,index) in list" :key="index" @tap="tourl">
				<view class="img">
					<image src="http://radio.newfeeling.cn/WechatIMG259.png" class="box_img" mode=""></image>
				</view>
				<div class="item-cont">
					<view class="info">
						<view class="name">玩家名称</view>
						<view class="desc">这是简介</view>
					</view>
					<view class="dz">
						<text class="icon">
							<image src="../../static/dz.png" class="dz_img" mode=""></image>
						</text>
						<text class="num">158</text>
					</view>
				</div>
			</view>
		
		</view>
		<view class="user_dz" @tap="toMake(1)">
			<view class="icon"></view>
			<view class="text">
				<text>个人</text>
				<text>定制</text>
			</view>
		</view>
		<view class="user_info" @tap="toMake(2)">
			<view class="icon"></view>
			<view class="text">
				<text>个人</text>
				<text>中心</text>
			</view>
		</view>
		<TabBar tabIndex=1></TabBar>
	</view>
</template>

<script>
	import TabBar from '../../components/jinjie-tabBar/jinjie-tabBar.vue' 
	export default {
		data() {
			return {
				title: '这是玩家故事站页面',
				list:[1,2,3,4,5,6,7,8,9,10]
			}
		},
		onLoad() {

		},
		components: {
			TabBar
		},
		methods: {
			tourl(){
				uni.navigateTo({
					url:"./details/details"
				})
			},
			toMake(type){
				if(type ==1){
					uni.navigateTo({
						url:"../usermake/usermake"
					})
				}else{
					uni.navigateTo({
						url:"../userinfo/userinfo"
					})
				}
			}
		}
	}
</script>

<style lang="scss">
.Story{
	background: $bgColor2;
	padding-bottom: 120upx;
	.nav{
		position: fixed;
		top: 0;
		left: 0;
		width: 100%;
		padding-top: 20upx;
		font-size: 28upx;
		background: $bgColor;
		text-align: center;
		border-bottom: 1upx solid #aaa;
		text{
			display: inline-block;
			padding: 0 30upx;
			color: #aaa;
			box-sizing: border-box;
			padding-bottom: 10upx;
			margin: 0 100upx;
			&.act{
				// font-size: 42upx;
				color: #fff;
				border-bottom: 2upx solid #fff;
			}
		}
	}
	.list{
		padding: 120upx 20upx 30upx;
		font-size: 0;
		.item{
			display: inline-block;
			width: 48%;
			margin-bottom: 40upx;
			.img{
				width: 100%;
				height: 600upx;
				background: #666;
				.box_img{
					width: 100%;
					height: 100%;
				}
			}
			&:nth-child(2n+1){
				margin-right: 3%;
			}
			.item-cont{
				display: flex;
				padding-top: 10upx;
				.info{
					flex: 1;
					color: #fff;
					padding:0 10upx;
					.name{
						
						font-size: 28upx;
					}
					.desc{
						font-size: 24upx;
					}
				}
				.dz{
					width: auto;
					.icon{
						display: block;
						width:43upx;
						height: 36upx;
						background: url(../../static/dz.png) no-repeat center center;
						background-size: 100% 100%;
						margin: 0 auto;
					}
					.num{
						font-size: 24upx;
						color: #fff;
						padding-top:8upx;
						display: block;
						color: #ff456c;
					}
				}
			}
			
		}
	}
	.user_dz,.user_info{
		position: fixed;
		bottom: 260upx;
		box-sizing: border-box;
		padding: 10upx 30upx 10upx 20upx;
		height: 100upx;
		line-height: 40upx;
		border-radius: 50upx;
		background: #333;
		color: #fff;
		right: 10upx;
		font-size: 24upx;
		display: flex;
		.icon{
			height: 60upx;
			width: 80upx;
			background: url(../../static/icon.png) no-repeat center center;
			background-size: auto 100%;
			margin-top: 10upx;
			margin-right: 10upx;
		}
		background: rgba(114,79,231,0.8);
		text{
			text-align: center;
			display: block;
		}
	}
	.user_info{
		bottom: 140upx;
		.icon{
			background-image: url(../../static/icon2.png);
		}
	}
}
</style>
