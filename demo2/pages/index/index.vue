<template>
	<view class="content">
		<!-- 轮播图 -->
		<swiper class="swiper" indicator-dots="true" autoplay="true" :interval="2000">
			<swiper-item v-for="i in list">
				<view class="swiper-item uni-bg-red">
					<image class="swiper-image custom-image-size" :src="i"></image>
				</view>
			</swiper-item>
		</swiper>

		<div class="scroll">
			<view>
				<scroll-view class="scroll-view_H" scroll-x="true" @scroll="scroll">
					<view id="demo1" class="scroll-view-item_H uni-bg-red">
						<img src="static/scroll1.png" alt="">
					</view>

					<view id="demo1" class="scroll-view-item_H uni-bg-red">
						<img src="static/scroll2.png" alt="">
					</view>

					<view id="demo1" class="scroll-view-item_H uni-bg-red">
						<img src="static/scroll3.png" alt="">
					</view>

					<view id="demo1" class="scroll-view-item_H uni-bg-red">
						<img src="static/scroll4.png" alt="">
					</view>

					<view id="demo1" class="scroll-view-item_H uni-bg-red">
						<img src="static/scroll5.png" alt="">
					</view>
					
					<view id="demo1" class="scroll-view-item_H uni-bg-red">
						<img src="static/scroll6.png" alt="">
					</view>
					
					<view id="demo1" class="scroll-view-item_H uni-bg-red">
						<img src="static/scroll7.png" alt="">
					</view>
				</scroll-view>
			</view>
		</div>


		<div>
			<view class="MsgList">
				<view class="MlSon" v-for="item in List" :key="item.id">
					<view class="MlSonvBox">
						<view class="SonOfImg">
							<image class="Img" :src="item.img"></image>
						</view>
						<view class="SonOfName">
							<view class="SNTop">
								{{item.title}}
							</view>
							<view class="SNBom">
								<view class="SBleft">
									{{item.msg}}
								</view>
								<view class="SBright">
									{{item.price}}
								</view>
							</view>
						</view>
					</view>
				</view>
			</view>
		</div>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				list: [
					'../../static/pic1.png',
					'../../static/pic2.png',
					'../../static/pic3.png',
				],
				List: [{
						id: 1,
						img: "../../static/food1.png",
						title: "家常炒面",
						msg: "特价优惠",
						price: "￥10"
					},
					{
						id: 2,
						img: "../../static/food2.png",
						title: "改良版夜市炒面",
						msg: "特别推荐",
						price: "￥11"
					},
					{
						id: 3,
						img: "../../static/food3.png",
						title: "鲜嫩多汁小笼包",
						msg: "今日特价",
						price: "￥12"
					},
					{
						id: 4,
						img: "../../static/food4.png",
						title: "蛋炒粉",
						msg: "今日推荐",
						price: "￥15"
					},
					{
						id: 5,
						img: "../../static/food5.png",
						title: "榨菜肉丝粉",
						msg: "五星推荐",
						price: "￥20"
					},
					{
						id: 6,
						img: "../../static/food6.png",
						title: "冰淇淋",
						msg: "不可错过",
						price: "￥30"
					},
					{
						id: 7,
						img: "../../static/food7.png",
						title: "大排档炒面",
						msg: "独家推荐",
						price: "￥50"
					},
				]
			}
		},
		onLoad() {

		},
		methods: {

		}
	}
</script>

<!-- 开启scss -->
<style lang="scss">
	.custom-image-size {
		width: 414px !important;
		height: 150px !important;
	}


	.swiper-image {
		text-align: center;
		max-width: 100%;
		max-height: 100%;
	}

	.scroll-view_H {
		white-space: nowrap;
		width: 100%;
	}

	.scroll-view-item_H {
		display: inline-block;
		width: 25%;
		height: 50rpx;
		line-height: 50rpx;

		img {
			width: 80rpx;
			height: 50px;
			margin-top: 10px;
			margin-bottom: 10px;
		}
	}

	$max:100%;

	.MsgList {
		width: 92%;
		margin-left: 4%;
		max-width: 690rpx;
		height: auto;

		.MlSon {
			border-radius: 12rpx;

			.MlSonvBox {
				padding: 24rpx 32rpx;
				height: 168rpx;
				display: flex;
				justify-content: space-around;
				background: #fff;
				// border: 1px solid red;
				margin-top: 10px;

				.SonOfImg {
					border: 1px solid green;
					width: 164rpx;
					height: $max;
					border-radius: 12rpx;
					overflow: hidden;

					.Img {
						width: $max;
						height: $max;
					}
				}

				.SonOfName {
					width: 428rpx;
					height: $max;

					.SNTop {
						width: $max;
						height: 88rpx;
						text-overflow: -o-ellipsis-lastline;
						overflow: hidden;
						text-overflow: ellipsis;
						display: -webkit-box;
						-webkit-line-clamp: 2;
						line-clamp: 2;
						-webkit-box-orient: vertical;
						line-height: 44rpx;
						color: #06121E;
						font-size: 28rpx;
					}

					.SNBom {
						width: $max;
						height: 34rpx;
						line-height: 34rpx;
						font-size: 24rpx;
						display: flex;
						justify-content: space-between;
						margin-top: 18rpx;
					}
				}
			}
		}
	}
</style>
