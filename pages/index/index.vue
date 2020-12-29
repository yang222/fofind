<template>
	
</template>
<script>

	export default {
		name: 'Swiper',
		data() {
			return {
				screenHeight: 0,
				animationData: {
					0:{},
					1:{},
					2:{}
				},
				title: '0',
				indicatorDots: false,
				autoplay: false,
				previousMargin: uni.upx2px(82)+'px',
				nextMargin: uni.upx2px(82)+'px',
				circular: true,
				zoomParam: 1.1,
				swiperCurrentIndex: 0,
				data: [],
				max: 0,
				imgs:[
					"http://radio.newfeeling.cn/WechatIMG259.png",
					"http://radio.newfeeling.cn/WechatIMG259.png",
					"http://radio.newfeeling.cn/WechatIMG259.png",
				]
			}
		},
		props:{
			uni:{
				type : String,
				default:null
			}
		},
		computed:{
			fullHeight() {
				const res = uni.getSystemInfoSync();
				return res.windowHeight - uni.upx2px(60) - (res.statusBarHeight+44)+'px';
			}
		},
		onLoad() {
			this.animation = uni.createAnimation();
			this.animation.scale(this.zoomParam).step();
			this.animationData[0] = this.animation.export();
		},
		
		methods: {
			toUrl(){
				uni.navigateTo({
					url:"./play/play"
				})
			},
			change(e) {
				this.swiperCurrentIndex = e.detail.current;
				this.title = e.detail.currentItemId;
				for (let key in this.animationData) {
					if (e.detail.currentItemId == key) {
						this.animation.scale(this.zoomParam).step();
						this.animationData[key] = this.animation.export();
					} else {
						this.animation.scale(1.0).step();
						this.animationData[key] = this.animation.export();
					}
				}
			}
		}
	}
</script>

<style lang="scss">
	
	.swipers{
		.swiper-container {
			display: flex;
			align-items: center;
			overflow: visible !important;
		}
		
		.swiper-item {
			display: flex;
			flex-wrap: wrap;
			justify-content: center;
			margin-left: auto;
			background: #aaa !important;
			margin-right: auto;
			height: 858upx;
			width: 530upx;
			line-height: 300upx;
			overflow: auto;
			text-align: center;
			broder-radius: 6upx;
			margin-bottom: 50upx;
		}
		
		
		
		.swiper-tall {
			// margin-top: 100rpx;
			// height: 1200upx !important;
			display: flex;
			align-items: center;
			overflow: visible !important;
		}
		
		
		
		.swiper-title {
			width: 750upx;
			text-align: center;
		}
	}

</style>
