<template>
	<view class="tab-block">
		<ul
			class='tab-list flex flex-center'
			:class="showMiddleButton === true?'tab-list-middle':'tab-list-default'"
		>
			<li
				v-for="(item, index) in tabList"
				class="list-item flex flex-column flex-middle"
				:class="{'active':selectTab == index,'middle':index == 1}"
				@click="handlePush(item, index)"
				:key="index"
			>
				<view class="item-img-box" :class="">
					<image
						class="item-img"
						:src="selectTab == index ? item.selectedIconPath : item.iconPath"
					/>
				</view>
				<view class="item-text font-20 color-black">
					{{item.text}}
				</view>
			</li>
		</ul>
		<view class="tab-bar" v-show="showTabBar === true"></view>
	</view>
</template>

<script>
	export default {
		props: {
			tabIndex: { //当前选中的tab项
				type: Number,
				default: 0,
			}
		},
		data() {
			return {
				/*
				 * iconPath: 默认icon图片路径
				 * selectedIconPath: 选中icon图片路径 
				 * text: tab按钮文字
				 * pagePath:页面路径
				 * middleClass:中间按钮样式类名
				 * tabList最小两项，最多五项
				 * tabList长度为奇数时，中间按钮才会突出显示
				 * 
				 */
				tabList: [{
						iconPath: '../../static/home.png',
						selectedIconPath: '../../static/home.png',
						text: '首页',
						pagePath: '/pages/home/home',
						middleClass: ''
					},
					{
						iconPath: '../../static/user.png',
						selectedIconPath: '../../static/user.png',
						text: '玩家故事站',
						pagePath: '/pages/story_station/story',
						middleClass: 'tabar2'
					},
					{
						iconPath: '../../static/play.png',
						selectedIconPath: '../../static/play_s.png',
						text: '有戏放映室',
						pagePath: '/pages/release/release',
						middleClass: ''
					}
				],
				showTabBar: false,
				showMiddleButton: false,
				selectTab:0,
			};
		},
		computed: {
			getHeight() {
				return Number(this.height);
			},
		},
		mounted() {
			this.selectTab = this.$props.tabIndex;
			this.getSystemInfo()
			this.setTabBar()
		},
		methods: {
			//判断中间按钮是否突出显示
			setTabBar(){
				let tabLength = this.tabList.length
				if (tabLength % 2) {
					this.showMiddleButton = true
					let middleIndex = Math.floor(tabLength / 2)
					this.tabList[middleIndex].middleClass = 'mid-button'
				}
			},
			//点击按钮
			handlePush(item, index) {
				console.log(item,index)
				if (this.tabIndex !== index) {
					console.log(`${item.pagePath}?tabIndex=${index}`)
					uni.reLaunch({
						url: `${item.pagePath}`,
					})
				}
				this.selectTab = index;
			},
			//兼容iPhoneX以上底部黑线条的显示
			getSystemInfo() {
				uni.getSystemInfo({
					success: (res) => {
						// X及以上的异形屏top为44，非异形屏为20
						if (res.safeArea.top > 20) {
							this.showTabBar = true
						}
					}
				});
			},
		}
	}
</script>

<style lang="scss">
	.flex {
		display: flex;
		flex-flow: row wrap;
	}

	.flex-center {
		align-items: center;
		justify-content: center;
	}

	.flex-column {
		flex-direction: column;
	}

	.flex-middle {
		align-items: center;
	}
	.font-20 {
		font-size: 20rpx;
	}
	.tab-block {
		position: fixed;
		bottom: 0;
		left: 0;
		z-index: 999;
		background-size: contain;
		width: 100vw;
		.tab-list{
			height:100rpx;
		}
		.tab-list-default{
			background-color: #FFFFFF;
			border-top: 1px #dddddd solid;
		}
		.tab-list-middle {
			position: relative;
			background: url('https://res.paquapp.com/popmartvip/home/nav_bar_bg_2x.png') no-repeat center center;
			background-size: cover;
		}
		.list-item {
			flex: 1;
			.item-img-box {
				width: 44rpx;
				height: 42rpx;
				margin-bottom: 9rpx;
				position: relative;
			}

			.item-img {
				width: 44rpx;
				height: 42rpx;
			}
			&.active{
				color: #fff;
			}
		}

		.mid-button,.middle {
			position: relative;
			.item-img-box {
				width: 86rpx;
				height: 86rpx;
				margin-bottom: 9rpx;
				position: absolute;
				z-index: 1002;
				top: -104rpx;
			}

			.item-img {
				width: 86rpx;
				height: 86rpx;
			}

			.item-text {
				font-size: 20rpx;
				position: absolute;
				z-index: 1002;
				bottom: -40rpx;
			}
		}

		.tab-bar {
			height: 30rpx;
			background-color: #FFFFFF;
		}
	}
	.tab-block{
		.tab-list{
			background: rgb(41,39,86) !important;
			color: #aaa;
			.mid-button,.middle {
				.item-img-box{
					background: $bgColor ;
					padding: 20upx;
					border-radius: 50%;
					top: -106rpx;
				}
			}
		}
	}
</style>
