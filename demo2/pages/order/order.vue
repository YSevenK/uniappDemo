<template>
	<view>
		<!-- 顶部导航栏 -->
		<view class="navbar">
			<view @tap="filterOrders('all')" :class="{ active: currentTab === 'all' }">全部订单</view>
			<view @tap="filterOrders('pending')" :class="{ active: currentTab === 'pending' }">待配送</view>
			<view @tap="filterOrders('completed')" :class="{ active: currentTab === 'completed' }">已完成</view>
		</view>


		<!-- 订单列表 -->
		<scroll-view class="order-list">
			<view class="order-item" v-for="order in filteredOrders" :key="order.id">
				<view class="table">
					<view class="table-row">
						<view class="table-cell">
							<text class="table-label">订单号:</text>
							<text class="table-value">{{ order.orderNumber }}</text>
						</view>
						<view class="table-cell">
							<text class="table-label">餐品信息:</text>
							<text class="table-value">{{ order.foodItems }}</text>
						</view>
					</view>
					<view class="table-row">
						<view class="table-cell">
							<text class="table-label">订单状态:</text>
							<text class="table-value">{{ order.status }}</text>
						</view>
						<view class="table-cell">
							<text class="table-label">价格:</text>
							<text class="table-value">{{ order.price }}</text>
						</view>
					</view>
					<view class="table-row">
						<view class="table-cell">
							<text class="table-label">配送地址:</text>
							<text class="table-value">{{ order.deliveryAddress }}</text>
						</view>
						<view class="table-cell">
							<text class="table-label">联系电话:</text>
							<text class="table-value">{{ order.contactNumber }}</text>
						</view>
					</view>
					<view class="table-row">
						<view class="table-cell">
							<text class="table-label">下单时间:</text>
							<text class="table-value">{{ order.orderTime }}</text>
						</view>
						<view class="table-cell">
							<text class="table-label">评分:</text>
							<text class="table-value">{{ order.rating }}</text>
						</view>
					</view>
					<view class="table-row">
						<view class="table-cell" colspan="2">
							<text class="table-label">评价:</text>
							<text class="table-value">{{ order.review }}</text>
						</view>
					</view>
				</view>
			</view>
		</scroll-view>
	</view>
</template>


<script>
	export default {
		data() {
			return {
				currentTab: 'all', // 当前选中的订单状态
				orders: [{
						id: 1,
						orderNumber: '12345',
						foodItems: '汉堡、薯条',
						status: '待配送',
						price: '￥20',
						deliveryAddress: '某某街道某某小区',
						contactNumber: '123-456-7890',
						orderTime: '2023-09-10 14:30'
					},
					{
						id: 2,
						orderNumber: '67890',
						foodItems: '披萨、可乐',
						status: '待配送',
						price: '￥30',
						deliveryAddress: '某某街道某某小区',
						contactNumber: '987-654-3210',
						orderTime: '2023-09-10 15:45'
					},
				],
				pending: [{
					id: 13214,
					orderNumber: '12345',
					foodItems: '汉堡、薯条',
					status: '待配送',
					price: '￥20',
					deliveryAddress: '某某街道某某小区',
					contactNumber: '123-456-7890',
					orderTime: '2023-09-10 14:30'
				}, ],
				completed: [{
					id: 13214,
					orderNumber: '10104840',
					foodItems: '汉堡、薯条',
					status: '待配送',
					price: '￥20',
					deliveryAddress: '某某街道某某小区',
					contactNumber: '123-456-7890',
					orderTime: '2023-09-10 14:30'
				}, ],
			};
		},
		computed: {
			// 根据当前选中的订单状态过滤订单列表
			filteredOrders() {
				if (this.currentTab === 'all') {
					return this.orders;
				} else if (this.currentTab === 'pending') {
					return this.pending;
				} else if (this.currentTab === 'completed') {
					return this.completed;
				}
			}
		},
		methods: {
			// 切换订单状态
			filterOrders(status) {
				this.currentTab = status;
			}
		}
	};
</script>

<style scoped>
	.navbar {
		display: flex;
		justify-content: space-around;
		background-color: #333;
		color: white;
		padding: 10px;
	}

	.navbar view {
		cursor: pointer;
	}

	.navbar view.active {
		text-decoration: underline;
	}

	.order-list {
		padding: 10px;
	}

	.order-item {
		background-color: #fff;
		border: 1px solid #ddd;
		border-radius: 8px;
		box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
		margin-bottom: 16px;
		padding: 16px;
	}

	.table {
		display: flex;
		flex-direction: column;
	}

	.table-row {
		display: flex;
		flex-direction: row;
		justify-content: space-between;
		margin-bottom: 8px;
	}

	.table-cell {
		flex: 1;
		display: flex;
		flex-direction: column;
	}

	.table-label {
		font-weight: bold;
		margin-bottom: 4px;
	}

	.table-value {
		white-space: pre-wrap;
	}
</style>
