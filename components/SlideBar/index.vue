<template>
	<view class="slide-bar">
		<view class="left">
			<view v-for="(item, index) in categoryList" @click="categoryClickEvent(item, index)" :key="item.id" :class="categoryNameActive === index ? 'name active' : 'name'">
				{{ item.name }}
			</view>
		</view>
		<view class="right">
			<scroll-view scroll-y :scroll-top="20">
				<view v-for="item in categoryList" :key="item.id" class="name">
					<text :class="'name' + item.id">{{ item.name }}</text>
					<view class="info-item" v-for="subItem in item.subCategoryList" :key="subItem.id">
						<image :src="subItem.image" />
						<view class="info">
							<text class="name">{{ subItem.name }}</text>
							<text class="desc">这是一段菜品介绍~~~~</text>
							<view class="btns">
								<button>+</button>
							</view>
						</view>
					</view>
				</view>
			</scroll-view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				categoryList: [{
					"id": "3",
					"name": "测试一级菜单1",
					"subCategoryList": [{
						"id": "10",
						"name": "测试二级菜单1-1",
						image: "http://gw.alicdn.com/bao/uploaded/i1/2091067499/TB1G2EHc1H2gK0jSZFEXXcqMpXa.png_290x10000.jpg_.webp"
					}, {
						"id": "11",
						"name": "测试二级菜单1-2",
						image: "http://gw.alicdn.com/bao/uploaded/i1/2091067499/TB1eyUmS7voK1RjSZFwXXciCFXa.png_290x10000.jpg_.webp"
					}, {
						"id": "12",
						"name": "测试二级菜单1-3",
						image: "http://gw.alicdn.com/bao/uploaded/i1/2091067499/O1CN01bxyQcD1CETxd3uDMG_!!2-item_pic.png_290x10000.jpg_.webp"
					}]
				}, {
					"id": "2",
					"name": "测试一级菜单2",
					"subCategoryList": [{
						"id": "7",
						"name": "测试二级菜单2-1",
						image: "http://gw.alicdn.com/bao/uploaded/i1/2091067499/O1CN01JME8QL1hn3yJjFmsC_!!2-item_pic.png_290x10000.jpg_.webp"
					}, {
						"id": "8",
						"name": "测试二级菜单2-3",
						image: "http://gw.alicdn.com/bao/uploaded/i1/2091067499/O1CN01SiNmgu1HJ84rwnlPw_!!2-item_pic.png_290x10000.jpg_.webp"
					}, {
						"id": "9",
						"name": "测试二级菜单2-2",
						image: "http://gw.alicdn.com/bao/uploaded/i1/2091067499/O1CN011KQrV8LEdxrFt7i_!!2468631159.png_290x10000.jpg_.webp"
					}]
				}, {
					"id": "1",
					"name": "测试一级菜单3",
					"subCategoryList": [{
						"id": "4",
						"name": "测试二级菜单3-1",
						image: "http://gw.alicdn.com/bao/uploaded/i1/2091067499/O1CN01pAbhJz1vmW7x7y6ni_!!0-item_pic.jpg_290x10000Q75.jpg_.webp"
					}, {
						"id": "5",
						"name": "查询测试专用",
						image: "http://gw.alicdn.com/bao/uploaded/i1/2091067499/TB1xYioVG6qK1RjSZFmXXX0PFXa.png_290x10000.jpg_.webp"
					}, {
						"id": "6",
						"name": "测试二级菜单3-2",
						image: "http://gw.alicdn.com/bao/uploaded/i1/2091067499/O1CN01hhMSW41GOKwzymt98_!!2935350612.jpg_290x10000Q75.jpg_.webp"
					}]
				}],
				categoryNameActive: 0, //当前选中active
				scrollTop: 0
			};
		},
		mounted() {
			
		},
		methods: {
			categoryClickEvent(item, index) {
				this.categoryNameActive = index;
				this.scrollTop = 100
			},
			scrollEvent(e) {
				
			},
		},
	}
</script>

<style lang="scss">
	.slide-bar {
		width: 100%;
		display: flex;
		.left {
			width: 200rpx;
			flex-shrink: 0;
			position: fixed;
			left: 24rpx;
			top: 130rpx;
			.name {
				padding-right: 10rpx;
				position: relative;
				overflow: hidden;
				text-overflow: ellipsis;
				white-space: nowrap;
				height: 80rpx;
				font-size: 36rpx;
				line-height: 80rpx;
				margin-bottom: 40rpx;
				&.active::after {
					content: "";
					position: absolute;
					right: 0;
					top: 50%;
					margin-top: -20rpx;
					height: 40rpx;
					border-radius: 30rpx;
					width: 8rpx;
					background-color: #BB3B32;
				}
			}
		}
	}
	.right {
		flex: 1;
		padding: 20rpx;
		height: 100%;
		margin-left: 200rpx;
	}
	.info-item {
		width: 100%;
		margin-top: 40rpx;
		display: flex;
		image {
			width: 200rpx;
			height: 200rpx;
		}
		.info {
			flex: 1;
			margin-left: 15rpx;
			display: flex;
			flex-direction: column;
			.name {
				font-size: 36rpx;
				margin-top: -10rpx;
			}
			.desc {
				margin-top: 10rpx;
				color: #696969;
				flex: 1;
				font-size: 28rpx;
			}
			.btns {
				align-self: flex-end;
				button {
					width: 50rpx;
					height: 50rpx;
					border-radius: 50%;
					display: flex;
					align-items: center;
					justify-content: center;
					background-color: #CB2B29;
					color: #fff;
				}
			}
		}
	}
</style>
