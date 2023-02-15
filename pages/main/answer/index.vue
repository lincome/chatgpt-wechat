<template>
	<view class="container">
		<view class="action">
			<view class="tips">
				ChatGPT官方接口通道
			</view>
			<view class="switch">
				<u-switch activeColor="#26B3A0" :value="true"></u-switch>
			</view>
		</view>
		<view class="answer">
			<view class="ask">{{prompt}}</view>
			<view class="content">
				{{rawHtml}}
			</view>
		</view>
		<view class="sheet">
			<view class="btn">
				<u-button open-type="share" icon="share" text="分享给好友"></u-button>
			</view>
			<view class="btn">
				<u-button iconColor="#ffffff" color="#26B3A0" icon="file-text" text="复制问题答案"></u-button>
			</view>
		</view>
	</view>
</template>
<!-- <script src="./static/jquery-1.12.4.js"></script> -->
<script>
	// import { ChatGPTAPI } from '../../../node_modules/chatgpt/build/index.js'
	
	export default {
		data() {
			return {
				rawHtml:'稍等...',
				prompt:'222'
			};
		},
		async onLoad() {
			// return
			var that = this;
			await uni.getStorage({
			  key: 'prompt',
			  success: function (res) {
				that.prompt = res.data.prompt;
			    console.log(that.prompt); // 输出：{name: 'John Doe', age: 30}
				// that.setData({
				//     prompt: that.prompt,
				// });
				uni.showLoading({
				  title: 'AI处理中'
				});
				
				wx.request({
				  url: 'https://api.openai.com/v1/completions',
				  method: 'POST',
				  header: {
				    'Authorization': `Bearer 。。。`,
				    'Content-Type': 'application/json'
				  },
				  data: JSON.stringify({
				    prompt: that.prompt,
					model: 'text-davinci-003',
				    max_tokens: 100,
				    temperature: 0.5,
				  }),
				  success(res) {
				    const response = res.data;
					that.rawHtml=response.choices[0].text
				  },
				  fail(error) {
				    console.error(error);
				  },
				});
				uni.hideLoading()
			  }
			})
			

		}
	}
</script>

<style lang="scss">
	.answer {
		width: 90%;
		margin: 0 auto;
		margin-top: 200rpx;
		z-index: -1;

		.ask {
			font-size: 36rpx;
			font-weight: bolder;
		}

		.content {
			margin-top: 30rpx;
			color: #606266;
		}
	}

	.action {
		width: 92%;
		position: fixed;
		bottom: 0rpx;
		top: 0rpx;
		display: flex;
		flex-direction: row;
		justify-content: space-between;
		height: 80rpx;
		align-items: center;
		box-shadow: 10rpx 10rpx 10rpx #eee;
		padding: 30rpx;
		z-index: 999;
		background-color: #fff;
	}

	.sheet {
		width: 100%;
		position: fixed;
		bottom: 0rpx;
		left: 0rpx;
		display: flex;
		flex-direction: row;
		justify-content: space-around;
		bottom: env(safe-area-inset-bottom);
		padding: 30rpx 0rpx;
		background-color: #fff;
		box-shadow: -10rpx -10rpx 10rpx #eee;

		.btn {
			width: 42%;

			.u-button {
				height: 90rpx;
			}
		}
	}
</style>
