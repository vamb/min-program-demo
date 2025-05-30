<template>
	<view class="content">
		<image class="logo" src="/static/logo.png"></image>
		<view class="text-area">
			<text class="title">{{title}}</text>
		</view>
	</view>
	<swiper class="swiper-banner" indicator-dots :circular="true" :autoplay="true">
		<swiper-item v-for="(item, index) in pictures" :key="index" >
			<image @tap="onPreviewImage(item.url)" :src="item.url" mode="aspectFit"></image>
		</swiper-item>
	</swiper>
</template>

<script>
	export default {
		data() {
			return {
				title: 'Hello uni',
				pictures: [
					{ id: 0, url: "/static/swiper/0.jpg" },
					{ id: 1, url: "/static/swiper/1.jpg" },
					{ id: 2, url: "/static/swiper/2.jpg" },
					{ id: 3, url: "/static/swiper/3.jpg" },
					{ id: 4, url: "/static/swiper/4.jpg" },
				]
			}
		},
		onLoad() {

		},
		methods: {
			onPreviewImage(url) {
				console.log('onPreviewImage url', url)
			}
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
	.swiper-banner, .swiper-banner image {
		width: 750rpx;
	}
</style>
