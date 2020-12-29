<template>
	<view class="release">
		<view class="img">
			<image src="http://radio.newfeeling.cn/WechatIMG264.png" class="tit_img" mode=""></image>
			<text class="icon"></text>
		</view>
		<view class="info">
			<view class="tit">第一集————陈泽彬 《长大的感觉》  </view>
			<view class="desc">视频描述文案视频描述文案视频描述文案视频描述文案视频描述文案视频描述文案视频描述文案视频描述文案视频描述文案视频描述文案视频描述文案</view>
		</view>
		<view class="list">
			<view class="item" :class="{'act':index == 0}" v-for="(item,index) in list" :key="index" @tap="tourl">
				<view class="img">
					<image src="http://radio.newfeeling.cn/WechatIMG264.png" class="tit_img" mode=""></image>
				</view>
				<view class="info">
					<text class="name">第一期——阿Bin</text>
					
				</view>
				<view class="desc">描述描述描述描述描述描述描述描述</view>
			</view>
			<view class="item more" >
				<view class="img">
					<text>敬请期待</text>
				</view>
				<view class="info">
					<text class="name">有戏人生，未完待续...</text>
					
				</view>
			</view>
		</view>
		<TabBar tabIndex=2></TabBar>
	</view>	
</template>

<script>
	import TabBar from '../../components/jinjie-tabBar/jinjie-tabBar.vue' 
	export default {
		components: {
			TabBar
		},
		data() {
			return {
				list:[1,2,3,4,5,6,7,8,9]
			}
		},
		methods: {
			
		}
	}
</script>

<style lang="scss">
.release{
	padding: 30upx 26upx 120upx;
	background: $bgColor2;
	.img{
		height: 400upx;
		// background: #aaa;
		// border-radius: 10upx;
		.tit_img{
			width: 100%;
			height: 100%;
		}
		position: relative;
		.icon{
			width: 120upx;
			height: 120upx;
			position: absolute;
			top: 50%;
			left: 50%;
			transform: translate(-50%,-50%);
			background: url(../../static/play_btn.png) no-repeat center center;
			background-size: 100% 100%;
		}
	}
	.info{
		padding-bottom: 40upx;
		.tit{
			padding: 10upx 0;
			font-size: 28upx;
			color: #fff;
		}
		.desc{
			font-size: 24upx;
			line-height: 42upx;
			color: #fff;
		}
	}
	.list{
		padding-top: 10upx;
		font-size: 0;
		.item{
			display: inline-block;
			width: 48%;
			vertical-align: top;
			margin-bottom: 20upx;
			
			.img{
				width: 100%;
				height: 200upx;
				box-sizing: border-box;
				background: #aaa;
				text{
					display: block;
					height: 200upx;
					border-radius: 5upx;
					text-align: center;
					line-height: 200upx;
					font-size: 32upx;
					color: #000;
					border: 2upx solid #2a294a;
				}
			}
			&.more{
				
				.img{
					height: 200upx !important;
					color: #706f83;
					background: #111031;
					text{
						font-size: 32upx;
						color: #706f83;
					}
				}
			}
			&.act{
				.img{
					border: 4upx solid #ff466c;
				}
			}
			&:nth-child(2n+1){
				margin-right: 3%;
			}
			.info{
				font-size: 32upx;
				display: flex;
				line-height: 40upx;
				padding-top: 10upx;
				padding-bottom: 0;
				.name{
					flex: 1;
					color: #fff;
					font-size: 28upx;
				}
				
			}
			.desc{
				font-size: 24upx;
				color: #fff;
				line-height: 42upx;
			}
		}
		
	}
}
</style>
