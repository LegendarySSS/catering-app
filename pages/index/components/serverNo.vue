<template>
	<view class="flow">
		<text>如果你喜欢，请关注我们的公众号，谢谢支持~</text>
		<view class="server">
			<image src="/static/images/photo.jpg"></image>
			<view class="center">
				<text>小宋的私房菜</text>
				<text class="desc">健康饮食，开心每一天~</text>
			</view>
			<button>关注</button>
		</view>
	</view>
</template>

<script>
</script>

<style lang="scss">
	.flow {
		box-shadow: 0 0 12rpx #d9d9d9;
		border-radius: 12rpx;
		padding: 16rpx;
		margin-top: 30rpx;
		.server {
			margin-top: 20rpx;
			display: flex;
			align-items: center;
			button {
				margin: 0;
				width: 140rpx;
				height: 70rpx;
				line-height: 70rpx;
				background-color: #5FCE73;
				color: #fff;
			}
			.center {
				display: flex;
				flex-direction: column;
				flex: 1;
				.desc {
					margin-top: 15rpx;
				}
			}
			image {
				width: 130rpx;
				height: 130rpx;
				border-radius: 50%;
				margin-right: 24rpx;
			}
		}
	}
</style>