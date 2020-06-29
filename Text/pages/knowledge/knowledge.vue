<template>
	<view class="box">
		<view class="back">
			<view class="head">
				<view class="head-img">
					<image class="img-head" src="../../static/logo.png"></image>
				</view>
				<view class="head-name">
					<view class="head-name-p">章鱼座</view>
				</view>
				<view class="head-log">
					<view class="log-p">项目经理</view>
				</view>
			</view>

			<view class="lunbo">
				<image src="../../static/logo.png"></image>
			</view>

			<view class="foot">
				<view class="foot-up">
					<view class="up-list">
						<view class="log-list" @click="personnel()">
							<view class="log-img">
								<image src="../../static/logo.png"></image>
							</view>
							<view class="log-name">
								<view class="name-p">人员管理</view>
							</view>
						</view>
						<view class="tis-s"></view>
						<view class="log-list" @click="knowledge()">
							<view class="log-img">
								<image src="../../static/logo.png"></image>
							</view>
							<view class="log-name">
								<view class="name-p">知识库管理</view>
							</view>
						</view>
						<view class="tis-s"></view>
						<view class="log-list" @click="tasks()">
							<view class="log-img">
								<image src="../../static/logo.png"></image>
							</view>
							<view class="log-name">
								<view class="name-p">任务管理</view>
							</view>
						</view>
					</view>
				</view>
				<view class="tis"></view>

				<view class="foot-down">
					<view class="down-list">
						<view class="log-list" @click="assessment()">
							<view class="log-img">
								<image src="../../static/logo.png"></image>
							</view>
							<view class="log-name">
								<view class="name-p">人员评估</view>
							</view>
						</view>
						<view class="tis-s"></view>
						<view class="log-list" @click="track()">
							<view class="log-img">
								<image src="../../static/logo.png"></image>
							</view>
							<view class="log-name">
								<view class="name-p">追踪管理</view>
							</view>
						</view>
						<view class="tis-s"></view>
						<view class="log-list" @click="out()">
							<view class="log-img">
								<image src="../../static/logo.png"></image>
							</view>
							<view class="log-name">
								<view class="name-p">退出登录</view>
							</view>
						</view>
					</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {

			}
		},
		onLoad() {
			uni.setNavigationBarColor({
				frontColor: '#000000',
				backgroundColor: '#ffffff',
			})
		},
		methods: {
			personnel: function() {
				// 弹窗
				uni.showModal({
					title: '人员管理',
				})
				// 跳转到导航页
				// uni.switchTab({
				// 	url: ''
				// })
				// 跳转到普通页
				// uni.navigateTo({
				// 	url: ''
				// })
			},
			knowledge: function() {
				uni.showModal({
					title: '知识库管理',
				})
			},
			tasks: function() {
				uni.showModal({
					title: '任务管理',
				})
			},
			assessment: function() {
				uni.showModal({
					title: '人员评估',
				})
			},
			track: function() {
				uni.showModal({
					title: '追踪管理',
				})
			},
			out: function() {
				uni.showModal({
					title: '退出登录',
				})
			},
		}
	}
</script>

<style>
	.box {
		width: 100%;
		height: 100%;
	}

	.back {
		width: 92%;
		height: 100%;
		margin-left: 4%;
	}

	image {
		width: 100%;
		height: 100%;
	}

	.head {
		width: 100%;
		height: 140px;
		float: left;
	}

	.head-img {
		width: 80px;
		height: 80px;
		float: left;
		margin-top: 30px;
	}

	.img-head {
		border-radius: 50%;
	}

	.head-name {
		width: 25%;
		float: left;
		margin-top: 55px;
	}

	.head-name-p {
		font-size: 24px;
		text-align: center;
		font-weight: lighter;
	}

	.head-log {
		width: 90px;
		float: left;
		margin-top: 60px;
		border-radius: 10px;
		background-color: red;
	}

	.log-p {
		font-size: 18px;
		text-align: center;
		font-weight: lighter;
		color: white;
	}

	.lunbo {
		width: 100%;
		height: 160px;
		float: left;
	}

	.foot {
		width: 100%;
		height: 261px;
		float: left;
		margin-top: 50px;
	}

	.foot-up {
		width: 100%;
		height: 110px;
		float: left;
	}

	.up-list {
		width: 100%;
		height: 80px;
		float: left;
	}

	.tis {
		width: 84%;
		height: 1px;
		float: left;
		margin-left: 8%;
		background-color: #C0C0C0;
	}

	.foot-down {
		width: 100%;
		height: 110px;
		float: left;
	}

	.down-list {
		width: 100%;
		height: 80px;
		float: left;
		margin-top: 30px;
	}

	.log-list {
		width: 33%;
		height: 100%;
		float: left;
	}

	.log-img {
		width: 45px;
		height: 45px;
		float: left;
		margin-top: 5px;
		margin-left: 35px;
		background-color: #4CD964;
	}

	.log-name {
		width: 100%;
		float: left;
		margin-top: 5px;
	}

	.name-p {
		font-size: 17px;
		text-align: center;
	}

	.tis-s {
		width: 1px;
		height: 100%;
		float: left;
		background-color: #C0C0C0;
	}
</style>
