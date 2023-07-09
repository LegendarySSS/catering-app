<template>
	<view class="product">
		<view class="product-item" v-for="item in list" :key="item.imageUrl">
			<image class="image" :src="item.imageUrl" />
			<text class="title">{{ item.name }}</text>
			<view class="price">
				￥<text class="now">{{ item.nowPrice }}</text>
				<text class="original">￥{{ item.originalPrice }}</text>
			</view>
			<text class="desc">有 {{item.comment >= 99 ? item.comment + '+' : item.comment }} 人觉得还不错</text>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				list: [
					{
						imageUrl: 'https://dummyimage.com/600x400/ffa991/fff',
						name: '红烧狮子头',
						nowPrice: 6.6,
						originalPrice: 18.8,
						comment: 99
					},
					{
						imageUrl: 'https://dummyimage.com/600x400/112233/fff',
						name: '酸辣土豆丝',
						nowPrice: 4.8,
						originalPrice: 16.8,
						comment: 99
					},
					{
						imageUrl: 'https://dummyimage.com/600x400/223344/fff',
						name: '干煸豆角',
						nowPrice: 1.8,
						originalPrice: 20.9,
						comment: 99
					}
				]
			}
		}
	}
</script>

<style lang="scss">
	.product {
		display: flex;
		flex-wrap: nowrap;
		box-sizing: border-box;
		overflow-x: scroll;
		padding-bottom: 10rpx;
		.product-item {
			border-radius: 12rpx;
			display: flex;
			flex-direction: column;
			box-shadow: 0 0 12rpx #d9d9d9;
			margin-right: 30rpx;
			min-width: 42%;
			.image {
				width: 100%;
				height: 200rpx;
				border-radius: 12rpx 12rpx 0 0;
			}
			.title {
				padding: 16rpx;
				font-weight: 700;
				font-size: 34rpx;
			}
			.price {
				padding: 0 16rpx;
				font-size: 28rpx;
				.now {
					font-size: 34rpx;
				}
				.original {
					text-decoration: line-through;
					margin-left: 10rpx;
					color: gray;
				}
			}
			.desc {
				padding: 16rpx;
				color: #646464;
				font-size: 26rpx;
			}
		}
	}
</style>