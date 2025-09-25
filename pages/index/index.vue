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
				<swiper-item v-for="item in 3">
					<image src="/common/images/banner1.jpg" mode="aspectFill"></image>
				</swiper-item>
			</swiper>
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
}
</style>