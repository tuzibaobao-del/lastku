<template>
	<view class="box">
		<view class="back">

			<view class="head">
				<view class="middle">
					<view class="middle-up">
						<view class="middle-left">
							<view class="head-img">
								<image class="img-head" src="../../static/logo.png"></image>
							</view>
						</view>
						<view class="middle-right">
							<view class="name">
								<view class="name-p">章鱼座</view>
							</view>
							<view class="title">
								<view class="title-p">人生就是一场说走就走的旅行，字数超过显示...</view>
							</view>
							<view class="change" @click="change()">
								<view class="change-p">修改信息</view>
							</view>
						</view>
					</view>
					<view class="tis"></view>

					<view class="middle-down">
						<view class="middle-s">
							<view class="num">
								<view class="num-p">85</view>
							</view>
							<view class="num-down">
								<view class="num-down-p">知识点掌握</view>
							</view>
						</view>
						<view class="middle-s">
							<view class="num">
								<view class="num-p">12</view>
							</view>
							<view class="num-down">
								<view class="num-down-p">已完成任务</view>
							</view>
						</view>
						<view class="middle-s">
							<view class="num">
								<view class="num-p">92</view>
							</view>
							<view class="num-down">
								<view class="num-down-p">参与项目数量</view>
							</view>
						</view>
					</view>
				</view>
			</view>
			<view class="tis-middle"></view>

			<view class="foot">
				<view class="foot-list" @click="input()">
					<view class="foot-img">
						<image src="../../static/logo.png"></image>
					</view>
					<view class="foot-text">
						<view class="text-p">信息录入</view>
					</view>
				</view>
				<view class="tis-s"></view>
				<view class="foot-list" @click="evaluating()">
					<view class="foot-img">
						<image src="../../static/logo.png"></image>
					</view>
					<view class="foot-text">
						<view class="text-p">职业评测</view>
					</view>
				</view>
				<view class="tis-s"></view>
				<view class="foot-list" @click="groups()">
					<view class="foot-img">
						<image src="../../static/logo.png"></image>
					</view>
					<view class="foot-text">
						<view class="text-p">我的小组</view>
					</view>
				</view>
				<view class="tis-s"></view>
				<view class="foot-list" @click="tasks()">
					<view class="foot-img">
						<image src="../../static/logo.png"></image>
					</view>
					<view class="foot-text">
						<view class="text-p">我的任务</view>
					</view>
				</view>
				<view class="tis-s"></view>
				<view class="foot-list" @click="work()">
					<view class="foot-img">
						<image src="../../static/logo.png"></image>
					</view>
					<view class="foot-text">
						<view class="text-p">工作情况</view>
					</view>
				</view>
				<view class="tis-s"></view>
				<view class="foot-list" @click="assessment()">
					<view class="foot-img">
						<image src="../../static/logo.png"></image>
					</view>
					<view class="foot-text">
						<view class="text-p">评估情况</view>
					</view>
				</view>
				<view class="tis-s"></view>
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
			change: function() {
				// 弹窗
				uni.showModal({
					title: '修改信息',
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
			input: function() {
				uni.showModal({
					title: '信息录入',
				})
			},
			evaluating: function() {
				uni.showModal({
					title: '职业评测',
				})
			},
			groups: function() {
				uni.showModal({
					title: '我的小组',
				})
			},
			tasks: function() {
				uni.showModal({
					title: '我的任务',
				})
			},
			work: function() {
				uni.showModal({
					title: '工作情况',
				})
			},
			assessment: function() {
				uni.showModal({
					title: '评估情况',
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
		width: 100%;
		height: 100%;
	}

	image {
		width: 100%;
		height: 100%;
	}

	.head {
		width: 100%;
		height: 241px;
	}

	.middle {
		width: 92%;
		height: 100%;
		float: left;
		margin-left: 4%;
	}

	.middle-up {
		width: 100%;
		height: 150px;
		float: left;
	}

	.middle-left {
		width: 36%;
		height: 100%;
		float: left;
	}

	.head-img {
		width: 90px;
		height: 90px;
		float: left;
		margin-left: 16px;
		margin-top: 30px;
	}

	.img-head {
		border-radius: 50%;
	}

	.middle-right {
		width: 64%;
		height: 100%;
		float: left;
	}

	.name {
		width: 100%;
		float: left;
		margin-top: 20px;
	}

	.name-p {
		font-size: 20px;
	}

	.title {
		width: 90%;
		height: 40px;
		float: left;
		margin-top: 10px;

		/* 超出显示省略号 */
		display: -webkit-box;
		-webkit-line-clamp: 2;
		overflow: hidden;
		-webkit-box-orient: vertical;
		text-overflow: ellipsis;
	}

	.title-p {
		font-size: 14px;
		color: #999999;
	}

	.change {
		width: 80px;
		height: 32px;
		float: left;
		margin-top: 10px;
		border-radius: 20px;
		background-color: #007AFF;
	}

	.change-p {
		margin-top: 5px;
		font-size: 15px;
		text-align: center;
		color: white;
	}

	.tis {
		width: 100%;
		height: 1px;
		float: left;
		background-color: #C0C0C0;
	}

	.middle-down {
		width: 100%;
		height: 90px;
		float: left;
	}

	.middle-s {
		width: 32%;
		height: 100%;
		float: left;
		margin-left: 1%;
	}

	.num {
		width: 100%;
		float: left;
		margin-top: 20px;
	}

	.num-p {
		font-size: 24px;
		text-align: center;
		font-weight: bold;
	}

	.num-down {
		width: 100%;
		float: left;
		margin-top: 10px;
	}

	.num-down-p {
		font-size: 14px;
		text-align: center;
		color: #999999;
	}

	.tis-middle {
		width: 100%;
		height: 10px;
		float: left;
		background-color: #F1F1F1;
	}

	.foot {
		width: 100%;
		height: 380px;
		float: left;
		margin-top: 10px;
	}

	.foot-list {
		width: 92%;
		height: 60px;
		float: left;
		margin-left: 4%;
	}

	.foot-img {
		width: 30px;
		height: 30px;
		float: left;
		margin-top: 15px;
		margin-left: 5px;
	}

	.foot-text {
		width: 25%;
		float: left;
		margin-top: 18px;
	}

	.text-p {
		font-size: 17px;
		text-align: center;
	}

	.tis-s {
		width: 92%;
		height: 1px;
		float: left;
		margin-left: 4%;
		background-color: #C0C0C0;
	}
</style>
