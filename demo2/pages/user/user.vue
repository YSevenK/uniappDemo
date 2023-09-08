<template>
	<view class="personal-center">
		<view class="user-info">
			<image class="avatar" src="../../static/logo.png" mode="aspectFill"></image>
			<view class="info-text">
				<text class="username">张三</text>
			</view>
		</view>

		<view class="menu">
			<view class="menu-item" @tap="editProfile">编辑个人资料</view>
			<view class="menu-item" @tap="changePassword">修改密码</view>
			<view class="menu-item" @tap="showLogoutConfirm">退出登录</view>
		</view>
	</view>
</template>

<script>
	export default {
		methods: {
			showLogoutConfirm() {
				uni.showModal({
					title: '退出登录',
					content: '确定要退出登录吗？',
					success: (res) => {
						if (res.confirm) {
							// 点击确定，退出登录操作
							this.logout();
						}
					},
				});
			},
		},
	};
</script>

<style scoped>
	.personal-center {
		padding: 20px;
	}

	.user-info {
		text-align: center;
		margin-bottom: 20px;
		display: flex;
		flex-direction: column;
		align-items: center;
	}

	.avatar {
		width: 80px;
		height: 80px;
		border-radius: 50%;
		margin-bottom: 10px;
	}

	.info-text {
		text-align: center;
	}

	.username {
		font-size: 18px;
		font-weight: bold;
	}

	.menu {
		background-color: #fff;
		border-radius: 10px;
		box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
	}

	.menu-item {
		padding: 15px 20px;
		border-bottom: 1px solid #eee;
		color: #333;
		font-size: 16px;
	}

	.menu-item:last-child {
		border-bottom: none;
	}
</style>
