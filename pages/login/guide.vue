<template>
	<view class="content" style="background-color: #000;">
		<swiper class="swiper" 
		:autoplay="autoplay" 
		:duration="duration">
			<swiper-item>
				<view class="swiper-item" >
					<view class="swiper-item-img" style="background-color:#211459 ;"><image src="/static/g1.jpg" mode="widthFix" ></image></view>
				</view>
				<view class="jump-over" @tap="launchFlag()">{{jumpover}}</view>
			</swiper-item>
			<swiper-item>
				<view class="swiper-item">
					<view class="swiper-item-img" style="background-color: #2c1156;"><image src="/static/g2.jpg" mode="widthFix" ></image></view>
				</view>
				<view class="jump-over" @tap="launchFlag()">{{jumpover}}</view>
			</swiper-item>
			<swiper-item>
				<view class="swiper-item">
					<view class="swiper-item-img" style="background-color: #390d58;"><image src="/static/g3.jpg" mode="widthFix" ></image></view>
				</view>
				<view class="jump-over" @tap="launchFlag()">{{jumpover}}</view>
			</swiper-item>
		</swiper>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				background: ['color1', 'color2', 'color3'],
				autoplay: true,
				duration: 500,
				jumpover: '跳过',
				experience: '立即体验'
			}
		},
		onLoad() {
			console.log('guide')
		},
		methods: {
			launchFlag: function(){
				// /**
				//  * 向本地存储中设置launchFlag的值，即启动标识；
				//  */
				// uni.setStorage({
				// 		key: 'launchFlag',
				// 		data: true,
				// });
				// uni.redirectTo({
				// 	url: '../sign_in/sign_in'
				// })
				uni.navigateTo({
					url: '/pages/login/sign_in'
				})
				
			}
		}
	}
</script>
<style>
	page,
	.content{
		width: 100%;
		height: 100%;
		background-size: 100% auto ;
		padding: 0;
		background-color: #454343
		
	}
	.swiper{
		width: 100%;
		height: 100%;
		background: #FFFFFF;
	}
	.swiper-item {
		width: 100%;
		height: 100%;
		text-align: center;
		position: relative;
		display: flex;
		/* justify-content: center; */
		align-items:flex-end;
		flex-direction:column-reverse
	}
	.swiper-item-img{
		width: 100%;
		height: 100%;
		margin: 0 auto;
		
	}
	.swiper-item-img image{
		width: 100%;
		height: 100%;
	}
	.uniapp-img{
		height: 100%;
		background: #FFFFFF;
		display: flex;
		justify-content: center;
		align-items:center;
		overflow: hidden;
	}
	.uniapp-img image{
		width: 40%;
	}
	
	.jump-over,.experience{
		position: absolute;
		height: 60upx;
		line-height: 60upx;
		padding: 0 40upx;
		border-radius: 30upx;
		font-size: 32upx;
		color: #454343;
		border: 1px solid #454343;
		z-index: 999;
	}
	.jump-over{
		right: 45upx;
		top: 125upx;
	}
	.experience{
		right: 50%;
		margin-right: -105upx;
		bottom: 0;
	}
</style>
