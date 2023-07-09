<template>
	<view class="content">
		<view class="user">
			<image class="profile-img" src="https://dummyimage.com/50x50/112345/fff" />
			<view class="profile">
				<text>微信网名</text>
				<text>Welcome，享受生活的乐趣~</text>
			</view>
		</view>
		<notice-bar />
		<view class="entry">
			<view class="item">
				<image src="/static/images/eat.png" class="bg-img"/>
				<text class="title">现做</text>
				<text class="desc">我饿了，马上就要吃~</text>
			</view>
			<view class="item">
				<image src="/static/images/order.png" class="bg-img"/>
				<text class="title">预约</text>
				<text class="desc">用心制作精美食品~</text>
			</view>
		</view>
		<server-no />
		<view class="hot">推荐美食</view>
		<Product />
		<view class="end">到底啦~</view>
	</view>
</template>

<script>
	import Product from '@/pages/index/components/product.vue';
	import ServerNo from '@/pages/index/components/serverNo.vue';
	import NoticeBar from '@/pages/index/components/noticeBar.vue'
	export default {
		components: {
			Product, ServerNo, NoticeBar
		}
	}
</script>

<style lang="scss">
	.content {
		box-sizing: border-box;
		padding: 0 20rpx;
		.entry {
			margin-top: 40rpx;
			height: 200px;
			display: flex;
			justify-content: space-between;
			.item {
				width: calc(50% - 15rpx);
				padding: 26rpx;
				box-shadow: 0 0 12rpx #d9d9d9;
				border-radius: 12rpx;
				display: flex;
				flex-direction: column;
				position: relative;
				.bg-img {
					position: absolute;
					width: 60%;
					height: 60%;
					right: 0;
					bottom: 0;
					z-index: -1;
				}
				.title {
					font-size: 48rpx;
				}
				.desc {
					margin-top: 12rpx;
					font-size: 30rpx;
				}
				&:first-child {
					margin-right: 30rpx;
				}
			}
		}
	}
	.user {
		background-color: #fff;
		border-radius: 12rpx;
		box-shadow: 0 0 12rpx #d9d9d9;
		padding: 18rpx;
		height: 90rpx;
		margin-top: -60rpx;
		position: relative;
		z-index: 99;
		display: flex;
		align-items: center;
		.profile-img {
			width: 80rpx;
			height: 80rpx;
			border-radius: 50%;
			margin-right: 34rpx;
		}
		.profile {
			display: flex;
			flex-direction: column;
			font-size: 32rpx;
		}
	}
	.end {
		margin: 30rpx 0;
		text-align: center;
	}
	.hot {
		margin: 30rpx 0;
		text-align: center;
		position: relative;
		&:before {
			content: "";
			position: absolute;
			width: 40%;
			height: 1px;
			background-color: #d9d9d9;
			top: 50%;
			left: 0;
		} 
		&:after {
			content: "";
			position: absolute;
			width: 40%;
			height: 1px;
			background-color: #d9d9d9;
			top: 50%;
			right: 0;
		}
	}
</style>