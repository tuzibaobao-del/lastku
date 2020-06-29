<template>
	<view class="purchased">
		<view class="head">
			<view class="purchased_font">已购</view>
			<view style="display: flex;align-items: center;">
				<image style="width: 40upx;height: 40upx;" src="../../../static/搜索.png"></image>
				<view class="purchased_quxiao" style="padding: 0 10upx 0 20upx;">最近学习</view>
				<image style="width: 20upx;height: 40upx;" src="../../../static/purchased/gengduo.jpg" @click="gengduo"></image>
			</view>
		</view>
		<view class="middle">
			<view class="middle_box">
				<view class="kaiguan" @click="xialas">
					<view class="kaiguan_back"></view>
					<view class="kai_box" v-if="kaiguan == true">
						<view class="kai"></view>
						<view class="kai" style="background-color: #FFA500;"></view>
					</view>
					<view class="kai_box" v-else>
						<view class="kai" style="background-color: #C0C0C0;"></view>
						<view class="kai"></view>
					</view>
				</view>
				<view class="kaiguan_font">隐藏学完</view>
			</view>
			<view style="display: flex;">
				<view class="kecheng_tab" @click="ones" v-if="one == false">课程</view>
				<view class="kecheng_tab2" @click="ones" v-else>课程</view>

				<view class="kecheng_tab" @click="twos" style="margin-left: 10upx;" v-if="two == false">听书书架</view>
				<view class="kecheng_tab2" @click="twos" style="margin-left: 10upx;" v-else>听书书架</view>

				<view class="kecheng_tab" @click="threes" style="margin-left: 10upx;" v-if="three == false">电子书架</view>
				<view class="kecheng_tab2" @click="threes" style="margin-left: 10upx;" v-else>电子书架</view>
			</view>
		</view>
		<view class="empty">
			<view style="margin-top: 200upx;">
				<image class="empty_img" src="../../../static/purchased/empty.png"></image>
				<view class="empty_font">什么都没有~</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				kaiguan: false,
				one: false,
				two: false,
				three: false
			}
		},
		onLoad() {

		},
		methods: {
			gengduo: function() {
				console.log('更多')
			},
			xialas: function() {
				this.kaiguan = !this.kaiguan
				console.log('隐藏学完')
			},
			ones: function() {
				this.one = !this.one
				console.log('课程')
			},
			twos: function() {
				this.two = !this.two
				console.log('听书书架')
			},
			threes: function() {
				this.three = !this.three
				console.log('电子书架')
			}
		}
	}
</script>

<style>
	.purchased {
		padding: 100upx 36.42upx;
	}

	.head {
		display: flex;
		justify-content: space-between;
		align-items: center;
	}

	.purchased_font {
		font-size: 56upx;
	}

	.purchased_quxiao {
		font-size: 34upx;
	}

	.middle {
		width: 100%;
		height: 142.85upx;
		display: flex;
		justify-content: space-between;
		align-items: center;
	}

	.middle_box {
		display: flex;
		justify-content: space-between;
		align-items: center;
	}

	.kaiguan {
		width: 57.14upx;
		height: 28.57upx;
		display: flex;
		justify-content: center;
		align-items: center;
		position: relative;
	}

	.kaiguan_back {
		width: 90%;
		height: 21.42upx;
		background-color: #C0C0C0;
		border-radius: 10upx;
	}

	.kai_box {
		display: flex;
		justify-content: space-between;
		position: absolute;
	}

	.kai {
		width: 28.57upx;
		height: 28.57upx;
		border-radius: 50%;
	}

	.kaiguan_font {
		font-size: 30upx;
		margin-left: 10upx;
	}

	.kecheng_tab {
		font-size: 30upx;
		padding: 0 20upx;
		border-radius: 30upx;
	}

	.kecheng_tab2 {
		font-size: 30upx;
		padding: 0 20upx;
		background-color: #FFA500;
		border-radius: 30upx;
	}

	.empty {
		width: 100%;
		height: 100%;
		display: flex;
		justify-content: center;
	}

	.empty_img {
		width: 600upx;
		height: 225upx;
	}

	.empty_font {
		width: 100%;
		text-align: center;
		font-size: 32upx;
	}
</style>
