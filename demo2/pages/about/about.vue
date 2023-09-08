<template>
	<view class="help-and-support">
		<view class="page-header">
			<text class="page-title">帮助与支持</text>
		</view>

		<view class="faq-section">
			<text class="section-title">常见问题</text>
			<view class="faq-item" v-for="(question, index) in faqList" :key="index">
				<text class="question">{{ question.question }}</text><br>
				<text class="answer" v-if="question.expanded">{{ question.answer }}</text>
				<text class="toggle-icon" @tap="toggleAnswer(index)">
					{{ question.expanded ? '收起答案' : '查看答案' }}
				</text>
			</view>
		</view>

		<view class="contact-section">
			<text class="section-title">联系我们</text><br>
			<text class="contact-info">客服电话: 123-456-7890</text><br>
			<text class="contact-info">电子邮件: abc@def.com</text>
		</view>

		<view class="version">
			<text class="version-text">V1.0</text>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				faqList: [{
						question: '如何下单？',
						answer: '您可以在首页浏览餐厅，选择菜品并将它们添加到购物车，然后结算订单。',
						expanded: false,
					},
					{
						question: '如何取消订单？',
						answer: '您可以在订单历史页面找到待配送的订单并取消它们。',
						expanded: false,
					},
				],
			};
		},
		methods: {
			toggleAnswer(index) {
				this.faqList[index].expanded = !this.faqList[index].expanded;
			},
		},
	};
</script>

<style scoped>
	.help-and-support {
		padding: 20px;
	}

	.page-header {
		text-align: center;
		margin-bottom: 20px;
	}

	.page-title {
		font-size: 24px;
		font-weight: bold;
	}

	.section-title {
		font-size: 20px;
		font-weight: bold;
		margin-bottom: 10px;
	}

	.faq-item {
		margin-bottom: 10px;
	}

	.question {
		font-weight: bold;
	}

	.toggle-icon {
		color: #007AFF;
		cursor: pointer;
	}

	.contact-info {
		margin-bottom: 10px;
	}

	.version {
		text-align: center;
		color: #ccc;
		margin-top: 120px;
	}

	.version-text {
		font-size: 14px;
	}
</style>
