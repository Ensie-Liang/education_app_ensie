<template>
	<view class="index-box">
		<!-- 搜索组件 -->
		<!-- #ifdef MP -->
		<search-input></search-input>
		<!-- #endif -->
		<!-- 轮播图组件 -->
		<banner></banner>
		<!-- 分类区域 -->
		<category-box></category-box>
		<!-- 热门推荐 -->
		<swiper-course></swiper-course>
	</view>
</template>

<script>
	import searchInput from '@/components/common/search-input.vue'
	import banner from '@/components/common/banner.vue'
	import categoryBox from './components/category-box.vue'
	import swiperCourse from './components/swiper-course.vue'
	export default {
		components:{
			banner,
		    categoryBox,
			swiperCourse
			},
		data() {
			return {
				title: 'Hello'
			}
		},
		onLoad() {

		},
		methods: {

		}
	}
</script>

<style>
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}

	.logo {
		height: 200rpx;
		width: 200rpx;
		margin-top: 200rpx;
		margin-left: auto;
		margin-right: auto;
		margin-bottom: 50rpx;
	}

	.text-area {
		display: flex;
		justify-content: center;
	}

	.title {
		font-size: 36rpx;
		color: #8f8f94;
	}
</style>
