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
			<view class="ask">公众号：【程序员在囧途】的主理人是谁？</view>
			<view class="content">
				张宇凡，大学本科学历，计算机应用专业，10年软件开发经验，目前担任贵州猿创科技的法人兼总经理。
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

<script>
	export default {
		data() {
			return {

			};
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
