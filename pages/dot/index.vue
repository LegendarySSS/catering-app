<template>
	<view class="container">
		<view class="head">
			<view class="input">
				<uni-icons type="search" />
				<input type="text" placeholder="请输入">
			</view>
			<view class="address">
				<view class="location">临河悦园4号院8号楼2单元</view>
				<uni-icons type="location" size="28"/>
			</view>
		</view>
		<view class="content">
			<slide-bar />
		</view>
		<view class="foot">
			<image src="/static/images/shop.png" class="shop-img" />
			<view class="base">
				<text class="price">合计：<text>￥</text>0元</text>
				<button>买单</button>
			</view>
		</view>
	</view>
</template>

<script>
	import SlideBar from '../../components/SlideBar/index.vue'
	export default {
		data() {
			return {
				
			}
		},
		components: {
			SlideBar
		}
	}
</script>

<style lang="scss">
	.container {
		padding: 0 24rpx;
		display: flex;
		height: 100%;
		flex-direction: column;
		.content {
			flex: 1;
			overflow: auto;
		}
	}
	.head {
		display: flex;
		height: 120rpx;
		align-items: center;
		.input {
			border: 1px solid #F7CB49;
			border-radius: 20rpx;
			height: 70rpx;
			flex: 1;
			display: flex;
			align-items: center;
			line-height: 1;
			padding: 0 20rpx;
			input {
				margin-left: 10rpx;
				border: none;
				outline: none;
			}
		}
		.address {
			width: 240rpx;
			display: flex;
			justify-content: space-between;
			align-items: center;
			margin-left: 15rpx;
			.location {
				overflow: hidden;
				text-overflow: ellipsis;
				white-space: nowrap;
			}
		}
	}
	.foot {
		height: 120rpx;
		display: flex;
		justify-content: space-between;
		align-items: center;
		.shop-img {
			width: 100rpx;
			height: 80rpx;
		}
		.base {
			display: flex;
			align-items: center;
			.price {
				margin-right: 26rpx;
				font-size: 38rpx;
				text {
					font-size: 32rpx;
				}
			}
			button {
				width: 200rpx;
				height: 80rpx;
				line-height: 80rpx;
				border-radius: 50rpx;
				color: #fff;
				background-color: #CB2B29;
			}
		}
	}
</style>
