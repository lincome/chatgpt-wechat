<template>
	<view class="container">
		<view class="form">
			<view class="logo">
				<u--image src="/static/wxlogo.png" shape="circle" width="200rpx" height="200rpx">
				</u--image>
			</view>
			<u-transition :show="true" mode="slide-left">
				<view class="title">ChatGPT专业版</view>
			</u-transition>
			<u-transition :show="true" mode="slide-right">
				<view class="desc">AI界的新神器，ChatGPT帮你写答案！</view>
			</u-transition>
			<!-- <view class="ad-box">
				<ad unit-id="adunit-4b7965e593733d4e"></ad>
			</view> -->
			<view class="btn-group">
				<view class="btn" v-on:click="onToForm">
					<u-button shape="circle" iconColor="#ffffff" color="#26B3A0" icon="edit-pen" text="免费注册体验">
					</u-button>
				</view>
				<!-- <view class="tips">
					目前我们通过AI实现自动生成壁纸，想体验的可以点击体验按钮
				</view>
				<view class="btn" v-on:click="toMiniProgram">
					<u-button shape="circle" iconColor="#ffffff" color="#26B3A0" text="体验小程序">
					</u-button>
				</view> -->
				<view class="btn">
					<u-button open-type="share" shape="circle" color="#26B3A0" :plain="true" icon="share" text="推荐给朋友"></u-button>
				</view>
			</view>
			<view class="desc-box">
				<view class="title">如何注册并且开启ChatGPT</view>
				<view class="cont">chatGPT 是一种使用GPT-3 模型训练的对话机器人。GPT-3 是 OpenAl 公司开发的一种语言生成模型，通过大量训练文本数据，它可以通过模仿人类语言来生成语言。chatGPT 可以使用这一技术来进行自然语言对话，回答用户的问题，或者进行自然语言文本生成任务。</view>
				<!-- <ad unit-id="adunit-eacac3d02a9631ba" ad-type="video" ad-theme="white"></ad> -->
				<view class="sub-title">1.官方网站 http://openai.com</view>
				<view class="sub-title">2.openai接口文档</view>
				<view class="sub-cont">https://beta.openai.com/docs/api-reference/introduction</view>
				<view class="sub-title">3.chatGPT 开源机器人</view>
				<view class="sub-cont">https://github.com/fuergaosi233/wechat-chatgpt</view>
				<view class="sub-title">4.chatGPT镜像网站</view>
				<view class="sub-cont">https://gpt.chatapi.art/</view>
				<!-- <ad-custom unit-id="adunit-debc1c1f6bfaf529"></ad-custom> -->
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {

			};
		},
		methods: {
			onToForm() {
				uni.switchTab({
					url: '/pages/main/form/index'
				})
			},
			toMiniProgram(appId,cUrl){
				uni.navigateToMiniProgram({
					appId: "wx461ff8f867f3d028",
					path: `${cUrl||""}`,
					extraData: {
					  
					},
					success(res) {
					  // 打开成功
					}
				})
			}
		}
	}
</script>

<style lang="scss">
	.form {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		margin-top: 30%;

		.title {
			font-size: 38rpx;
			font-weight: bolder;
			margin-top: 15rpx;
		}

		.desc {
			margin-top: 15rpx;
			font-size: 28rpx;
			color: #666;
		}
		.ad-box{
			margin-top: 20px;
		}
		.btn-group {
			width: 80%;
			.tips{
				color: red;
			}
			.btn {
				margin: 30rpx 0rpx;

				.u-button {
					height: 100rpx;
				}
			}
		}
		.desc-box{
			margin: 0 30rpx;
			padding-bottom: 50rpx;
			.title{
				text-align: center;
				margin-bottom: 50rpx;
			}
			.cont{
				margin-top: 30rpx;
			}
			.sub-title{
				margin-top: 60rpx;
				font-weight: bolder;
			}
			.sub-cont{
				margin-top: 20rpx;
			}
		}
	}
</style>
