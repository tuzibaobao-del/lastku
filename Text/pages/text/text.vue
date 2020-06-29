<template>
	<view class="">
		<view class="box">
			<image src="../../static/dui.png" style="width: 80%;height: 80%;" v-show="showUpImg" @click="changeImg"></image>
			<image src="" style="width: 80%;height: 80%;" v-show="!showUpImg" @click="changeImg"></image>
		</view>
		
		
		<scroll-view scroll-x="true" style="width: 100%;white-space: nowrap;">
			<view style="padding-left: 35.71upx;">
				<view class="qijian" v-for="item in qijian" @click="sitelist">
					<view class="qijian_box" :style="{backgroundImage:'url('+ item.image +')'}">
						<view class="qijian_box_cont">
							<view style="font-size: 31.42upx;">{{item.city}}</view>
							<view style="font-size: 22.85upx;">{{item.place}}</view>
						</view>
						<view class="qijian_cont">
							<view style="font-size: 22.85upx;color: white;">详情</view>
							<image class="qijian_cont_img" src="../../static/right.png"></image>
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
				showUpImg: false,
				
				qijian: [{
						image: '../../static/site/site_yel.jpg',
						city: '天津市',
						place: '北辰1站'
					},
					{
						image: '../../static/site/site_yel.jpg',
						city: '天津市',
						place: '北辰2站'
					},
					{
						image: '../../static/site/site_yel.jpg',
						city: '天津市',
						place: '北辰3站'
					}
				],
			}
		},
		methods: {
			changeImg: function() {
				this.showUpImg = !this.showUpImg
			}
		}
	}
</script>
<style>
	.box {
		width: 48upx;
		height: 48upx;
		border-radius: 8upx;
		background-color: #999999;
		display: flex;
		justify-content: center;
		align-items: center;
	}
	
	/* 旗舰站点 */
	.qijian_font {
		padding-top: 57.14upx;
		padding-bottom: 27.85upx;
		padding-left: 36.42upx;
		font-size: 28.57upx;
	}
	
	.qijian {
		width: 242.85upx;
		height: 171.42upx;
		margin-right: 21.42upx;
		border-radius: 22.85upx;
		display: inline-block;
		padding-bottom: 20upx;
	}
	
	.qijian_box {
		width: 242.85upx;
		height: 171.42upx;
		border-radius: 22.85upx;
		background-size: 100% 100%;
	}
	
	.qijian_box_cont {
		padding-left: 27.85upx;
		padding-top: 25.71upx;
		color: white;
	}
	
	.qijian_cont {
		margin-top: 36.42upx;
		margin-left: 27.85upx;
		display: flex;
		align-items: center;
	}
	
	.qijian_cont_img {
		width: 21.42upx;
		height: 21.42upx;
		margin-left: 3px;
	}
</style>
