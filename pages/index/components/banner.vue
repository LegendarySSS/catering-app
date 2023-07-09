<template>
	<uni-swiper-dot class="uni-swiper-dot-box" @clickItem=clickItem :info="imgUrls" :dotsStyles="dotsStyles" :current="current" mode="default" field="content">
		<swiper @change="change" class="swiper" circular autoplay :interval="2000" :duration="500">
			<swiper-item v-for="item in imgUrls" :key="item">
				<view class="swiper-item">
					<image :src="item" class="img" />
				</view>
			</swiper-item>
		</swiper>
	</uni-swiper-dot>
</template>

<script>
	export default {
		data() {
			return {
				imgUrls: [
				  'https://dummyimage.com/600x400/7194d9/fff',
				  'https://dummyimage.com/600x400/992399/fff',
				  'https://dummyimage.com/600x400/044878/fff',
				  'https://dummyimage.com/600x400/aed61c/fff'
				],
				swiperDotIndex: 0,
				current: 0,
				dotsStyles: {
					bottom: 40,
					backgroundColor: 'rgba(0, 0, 0, .4)',
					selectedBackgroundColor: '#fff'
				}
			}
		},
		methods: {
			clickItem(e) {
				this.swiperDotIndex = e
			},
			change(e) {
				this.current = e.detail.current
			},
		}
	}
</script>

<style lang="scss">
	.swiper {
		width: 100%;
		height: 500rpx;
		.swiper-item {
			width: 100%;
			height: 100%;
			.img {
				width: 100%;
				height: 100%;
			}
		}
	}
</style>