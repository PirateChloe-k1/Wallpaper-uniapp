<template>
	<view class="homeLayout">
		<!-- 轮播图 -->
		<view class="banner">
			<!-- indicator-dots是轮播图的指示器 -->
			<!-- indicator-color指示器小圆点的颜色 -->
			<!-- indicator-active-color指示器当前被选中的小圆点的颜色 -->
			<!-- autoplay自动播放 -->
			<!-- circular使用衔接滑动 -->
			<swiper 
			indicator-dots indicator-color="rgba(255,255,255,0.5)" 
			indicator-active-color="#fff"
			autoplay
			circular
			>
				<swiper-item>
					<image src="/common/images/banner1.jpg" mode="aspectFill"></image>
				</swiper-item>
				<swiper-item>
					<image src="/common/images/banner2.jpg" mode="aspectFill"></image>
				</swiper-item>
				<swiper-item>
					<image src="/common/images/banner3.jpg" mode="aspectFill"></image>
				</swiper-item>
			</swiper>
		</view>
		
		<!-- 公告部分 -->
		<view class="notice">
			<view class="left">
				<uni-icons type="sound-filled" size="20" color="#28b389"></uni-icons>
				<text class=text>公告</text>
			</view>
			<view class="center">
				<!-- vertical轮播方向为纵向 -->
				<!-- autoplay自动播放 -->
				<!-- interval自动播放的时间间隔 -->
				<!-- duration轮播切换的动画时长 -->
				<!-- circular无限循环轮播 -->
				<swiper vertical autoplay interval="1500" duration="300" circular>
					<swiper-item v-for="item in 4">文字内容文字内容文字内容文字内容文字内容文字内容</swiper-item>
				</swiper>
			</view>
			<view class="right">
				<uni-icons type="right" size="16" color="#333"></uni-icons>
			</view>
		</view>
		
		<view class="select">
			<common-title>
				<template #name>每日推荐</template>
				<template #custom>
					<view class="date">
						<uni-icons type="calendar" size="18" color="#28b389"></uni-icons>
						<view class="text">
							<uni-dateformat :date="Date.now()" format="yyyy年MM月"></uni-dateformat>
						</view>
					</view>
				</template>
			</common-title>
			<view class="content">
				<scroll-view scroll-x>
					<view class="box" v-for="item in 8">
						<image src="../../common/images/preview_small.webp" mode="aspectFill"></image>
					</view>
				</scroll-view>
			</view>
		</view>
		
		<view class="theme">
			<common-title>
				<template #name>专题精选</template>
				<template #custom>
					<navigator url="" class="more">More+</navigator>
				</template>
			</common-title>
		</view>
	</view>
</template>

<script setup>
	
</script>

<style lang="scss" scoped>
.homeLayout{
	.banner{
		width: 750rpx;
		padding: 30rpx 0;
		
		swiper{
			// width: 750rpx;
			width: 100%;
			height: 340rpx;
			
			&-item{
				width: 100%;
				height: 100%;
				padding: 0 30rpx;
				
				image{
					width: 100%;
					height: 100%;
					border-radius: 10rpx;
				}
			}
		}
	}
	.notice{
		width: 690rpx;
		height: 80rpx;
		line-height: 80rpx;
		background: #f9f9f9;
		margin: 0 auto;
		border-radius: 80rpx;
		display: flex;
		.left{
			width: 140rpx;
			display: flex;
			justify-content: center;
			align-items: center;
			.text{
				color: #28b389;
				font-weight: 600;
				font-size: 28rpc;
			}
		}
		// flex: 1让元素自适应填充父容器的剩余空间 并且在空间变化时（如窗口缩放）能灵活伸缩
		.center{
			flex: 1;
			swiper{
				height: 100%;
				&-item{
					height: 100%;
					font-size: 30rpx;
					color: #666;
					// 隐藏溢出内容
					overflow: hidden;
					// 文本强制一行显示
					white-space: nowrap;
					// 溢出部分用...提示
					text-overflow: ellipsis;
				}
			}
		}
		.right{
			width: 70rpx;
			display: flex;
			align-items: center;
			justify-content: center;
		}
	}
	.select{
		padding-top: 50rpx;
		.date{
			color: #28b389;
			display: flex;
			align-items: center;
			.text{
				margin-left: 5rpx;
			}
		}
		.content{
			width: 720rpx;
			margin-left: 30rpx;
			margin-top: 30rpx;
			scroll-view{
				white-space: nowrap;
				.box{
					width: 200rpx;
					height: 430rpx;
					display: inline-block;
					margin-right: 15rpx;
					image{
						width: 100%;
						height: 100%;
						border-radius: 10rpx;
					}
				}
				.box:last-child{
					margin-right: 30rpx;
				}
			}
		}
	}
	.theme{
		padding-top: 50rpx;
		.more{
			font-size: 32rpx;
			color: #888;
		}
	}
}
</style>