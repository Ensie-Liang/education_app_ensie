<template>
	<view class="banner-box">
		<!-- 轮播图背景 -->
		<view class="banner-bg" :style="{'backgroundImage': `linear-gradient(${bannerBackground || '#009B8C'} 50%, #FFF)`}"></view>
		<!-- 轮播图 -->
		<swiper class="banner-swiper" indicator-dots indicator-color="rgba(255, 255, 255, 0.5)" 
		indicator-active-color="#FFFFFF"
		autoplay interval="4000" current="current" @change="SwiperChange">
			<swiper-item class="swiper-item" v-for="(item, index) in bannerList" :key="index">
				<image src="item.imageUrl"></image>
			</swiper-item>
		</swiper>
	</view>
</template>

<script>
	export default {
		props: {
			bannerList: {
				type: Array,
				default: () => [
								{
									id: 1,
									imageUrl: '/static/images/it01.png',
									background: '#009B8C',
									// advertUrl: '/pages/course/course-details'
								},
								{
									id: 2,
									imageUrl: '/static/images/it02.png',
									background: '#6E3DE6',
									// advertUrl: '/pages/course/course-details'
								},
								{
									id: 3,
									imageUrl: '/static/images/it03.png',
									background: '#0D81ED',
									// advertUrl: '/pages/course/course-details'
								},
								{
									id: 4,
									imageUrl: '/static/images/it04.png',
									background: '#009700',
									// advertUrl: '/pages/course/course-details'
								},
							]
			}
		},
		data() {
				return {
						current: 0, //当前所在滑块的 index
						bannerBackground: '#009B8C' // 背景色
				}
				},
		methods: {
				    SwiperChange(e) {
						this.current = e.detail.current
						this.bannerBackground = this.bannerList[e.detail.current].background;
					}
				}
	}
</script>

<style lang="scss">
	.banner-box {
		padding-top: 80rpx;
		
		/*#ifdef APP-PLUS*/
		padding-top: calc(var(--status-bar-height) + 80rpx);
		/*#endif*/
		
		.banner-bg {
			position: absolute;
			top: 0;
			width: 100%;
			height: 470rpx;
			background-image: linear-gradient(blue 10%, #FFF); //渐变色
			transform: .5s;
		}
		.banner-swiper {
			width: 100%;
			height: 350rpx;
			.swiper-item{
				width: 100%;
				height: 100%;
				padding: 0 30rpx;
				image {
					width: 100%;
					height: 100%;
					border-radius: 15rpx;
				}
			}
		}
	}
</style>