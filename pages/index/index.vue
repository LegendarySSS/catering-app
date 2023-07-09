<template>
	<view>
		<Banner />
		<Content />
	</view>
</template>

<script>
	import Banner from '@/pages/index/components/banner.vue';
	import Content from '@/pages/index/components/content.vue';
	export default {
		components: {
			Banner, Content
		},
	}
</script>

<style lang="scss">
	/deep/ .uni-swiper__dots-box {
		justify-content: initial!important;
		left: 25rpx!important;
	}
</style>
