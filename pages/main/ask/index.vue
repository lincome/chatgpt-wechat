<template>
	<view class="container">
		<view class="bg"></view>
		<view class="form">
			<view class="header">
				<view class="title">人工智能回答你需要的问题</view>
			</view>
			<block v-for="(item,index) in qList">
				<view class="panel" :class="'panel'+index">
					<view class="head">
						<view class="title">问：{{item.title}}</view>
					</view>
					<view class="content" :class="[{'example':cIndex===index}]" @click="onClickContent(index)">
						<rich-text :nodes="item.content"></rich-text>
					</view>
					<view class="bottom">
						ChatGPT回答时间：{{item.time}}
					</view>
				</view>
				<!-- <view v-if="index===0" class="ad-box"><ad unit-id="adunit-512f87e547fb53d5"></ad></view> -->
				<!-- <view v-if="index===4" class="ad-box"><ad-custom unit-id="adunit-debc1c1f6bfaf529"></ad-custom></ad></view> -->
				<!-- <view v-if="index===9" class="ad-box"><ad unit-id="adunit-eacac3d02a9631ba" ad-type="video" ad-theme="white"></ad></ad-custom></ad></view> -->
			</block>
		</view>
	</view>
</template>

<script>
	// 在页面中定义插屏广告
	let interstitialAd = null
	export default {
		data() {
			return {
				cIndex:'',
				pageScrollTop:0,
				qList:[
					{
						title:"在末来的社会发展中，计算机科学与技术将继续发挥着重要作用？",
						content:"在未来的社会发展中，计算机科学与技术将继续发挥着重要作用。随着科技的不断进步，计算机科学与技术将在越来越多的领域发挥作用。首先，计算机科学与技术将在人工智能领域发挥更大作用。人工智能是当前科技发展的热点之一，它将在各个领域产生广泛影响。例如，人工智能在医疗、金融、交通等领域都有着重要应用。其次，计算机科学与技术将在互联网和物联网领域发挥更大作用。互联网和物联网技术的发展将使得各种设备和服务能够相互连接，构建智能化城市和智能家居等。最后，计算机科学与技术将在数据分析领域发挥更大作用。随着大数据技术的发展，数据分析将在冬个领域产生重要影响。例如，数据分析在市场营销、管理决策等领域都有着重要应用。总之，计算机科学与技术将在未来的社会发展中继续发挥着重要作用，对各个领域产生广大影响",
						time:'2023-01-19 16:28:47'
					},
					{
						title:"你是gpt3.0模型吗",
						content:"是的，我是GPT-3 模型。GPT-3 是OpenAI公司开发的一种自然语言处理模型。它采用了预训练语言模型(PLM)的技术，可以在给定的任务上表现出很高的准确性。GPT-3模型的训练数据来自互联网上的大量文本其中包括了各种不同类型的文本，如新闻、博客、社交媒体等。GPT-3 模型在自然语言生成、问答、机器翻译等多种任务上都表现出了很高的水平。它可以生成非常逼真的文本，甚至可以模拟人类的写作风格和思维方式。此外，GPT-3 模型还可以进行多种自然语言理解任务，如问答、文本分类和情感分析等。GPT-3 模型的出现引发了广泛的关注，被管为是目前最先进的NLP模型之一。然而，在使用 GPT-3 模型时，需要注意它的局限性和限制，如它对于不熟悉的领域和语言的支持较弱因此，在实际应用中，需要根据具体任务的需求来选择合适的模型。",
						time:'2023-01-18 10:37:17'
					},
					{
						title:"我想拍一个视频来介绍深圳的吃喝玩乐",
						content:"深圳是一个繁华的城市，有很多吃喝玩乐的好地方。首先，深圳是美食天堂，有各种各样的美食，从传统的粤菜到外国美食都有。特别推荐深圳的火锅店，有很多不司口味的火锅，值得一尝。其次，深圳有很多娱乐场所，如海上世界，欢乐谷等。海上世界是一个大型水族馆，有各种各样的海洋生物展示，是学习海洋知识的好地方。欢乐谷是一个大型主题公园，有很多刺激的游乐设施，是放松娱乐的好去处。最后，深圳还有很多购物场所，如华强北电子城，深圳福田口岸购物城等。华强北电子城是全国最大的电子产品批发市场，有各种各样的电子产品。深圳福田口岸购物城是一个大型购物中心，有很多商店和餐厅，是逛街购物的好地方。总之深圳是一个充满活力的城市，有很多吃喝玩乐的好地方。拍一个视频来介绍深圳的吃喝玩乐是一个不错的主意，可以让更多人了解这个美丽的城市。",
						time:'2023-01-12 18:33:22'
					},
					{
						title:"怎么约心仪的女孩出来玩?",
						content:"约会心仪的女孩需要一些技巧和策略。以下是一些建议:<br><br>开始前先建立联系:在约会之前，你需要先和她建立联系。可以通过社交媒体或者其他渠道来了解她的兴趣和兴奋点。<br>确定她的兴趣:确定她的兴趣之后，你可以提供一些她喜欢的活动或场所<br>确保约会计划是安全的:确保约会地点是安全的，并且确保她有足够的时间来做她自己的事情。<br>让约会有趣:让约会有趣是非常重要的。你可以尝试提供一些有趣的活动或场所，如去看电影、公园野餐、游玩游乐场等。<br>成实直率:在约会过程中，诚实和直率是非常重要的请直接告诉她你的感受和想法，这样她就能更好的了解你。<br>保持联系: 约会之后，记得与她保持联系，告诉她你还想再见她.",
						time:'2023-01-19 22-53-53'
					},
					{
						title:"有一只小狐狸叫做Rex，他有三只小鱼朋友起生活在同一个大房子里面，请写一篇童话故事",
						content:"有一只可爱的小狐狸，名字叫Rex。他生活在一个大房子里，有三个小鱼朋友陪伴左右。一天，Rex跟他的三个小鱼朋友讨论了一个问题:“我们要去哪里玩呢?”小色们提出了各种不同的建议，但是Rex想了一想，他有一个更好的主意:“为什么不去山上，看看大自然的美景呢?”小鱼们都很高兴，立刻点头答应。他们一起走到山上，玩得非常开心。他们爬山，游泳，做各种各样的游戏。小鱼们对这里的美景非常惊讶，他们看到了阳光下的山峦、蓝蓝的天空和清澈的溪流。突然，Rex的朋友们发现了一只可怜的小鸟，它的翅膀受伤了，无法飞翔。小鱼们很关心这只小鸟，于是Rex决走帮助它。他找到了一棵大树，在树下建了一个小窝，并照顾这只小鸟，给它带来了食物和水。渐渐地，这只小鸟的翅膀开始愈合，最后，它再次飞翔了。小鱼们非常高兴，他们知道他们帮助了一个生命。这是一个关于友谊、关心和",
						time:'2023-02-02 08:17:02'
					},
					{
						title:"如何选择一支好的股票?",
						content:"选择一支有潜力的股票需要考虑多种因素。<br>首先，技术分析可以帮助您了解股票的价格走势。您可以使用技术指标，如移动平均线、布林带和指数平均指标来研究股票的走势。当短期移动平均线(如20天移动平均线)上穿长期移动平均线(如50天移动平均线)产生金叉现象。这通常被视为股票价格上涨的信号，可以考虑买入。当短期移动平均线下穿长期移动平均线产生死叉现象。这通常被视为股票价格下跌的信号，可以考虑卖出或观望。<br>此外，金融知识可以帮助您了解公司的财务状况。您可以研究公司的财报，了解其盈利能力、偿债能力和成长性。最后，您还可以了解公司的行业状况和政治、经济环境对该公司和行业的影响。值得注意的是，中国的股市发展的并不完善，选择一支有潜力的股票需要综合考虑技术分析、金融知识和其他因素。建议您对股票进行全面的研究，并且在确定投资策略时考虑自己的风险偏好.",
						time:'2023-01-19 22:53:36'
					},
					{
						title:"写一本异世界穿越小说的大纲",
						content:"一、故事背景:本故事背景为中世纪，存在着女巫和魔法。主人公是一名平凡的少年，在偶然的机会下穿越到了这个世界。<br>二、主人公的初始状态:主人公最初在穿越后很迷茫不知道自己来到了哪里。他需要适应这个充满魔法和女巫的世界。<br>三、主人公的目标:主人公的目标是找到回家的路，并在这个世界上生存下去。他需要寻找资源和朋友来帮助自己适应新的环境。<br>四、阻碍和危机:主人公会面临各种各样的阻碍和危机，如果他不能适应这个世界，他就会被危险所威胁他需要学习如何使用魔法来保护自己，同时还要面对来自当地势力的威胁。<br>五、主人公的成长和变化: 随着故事的进程，主人公会不断成长和变化。他会学会使用魔法，并逐渐了解这个世界的历史和文化。他也会变得更加坚强和独立.<br>六、结局:在故事的结局，主人公会找到回家的路并决定是否留在这个世界。他也会做出是否继续成为一名魔法师的决定。",
						time:'2023-01-19 22-53:56'
					},
					{
						title:"我是英语老师，请帮我出一道阅读理解习题",
						content:"阅读材料:<br>The Importance of Sleep<br><br>Sleep is essential for our overall health and well-being.Itallows our bodies to rest and repair, and it helps us to feelrefreshed and energized when we wake up.However,manpeople don't get enough sleep, and this can lead to a host ohealth problems. Lack of sleep can affect our mood, ourability to think and concentrate, and our overall physicalhealth It can also increase our risk of developing serioushealth conditions such as obesity. diabetes, and heart diseasMoreover, lack of sleep has been linked to an increased rislof accidents and injuries, making it particularly dangerousfor people who operate heavy machinery or drive longdistances. To ensure that we get enough sleep, it's importarito establish a consistent sleep schedule. Going to bed andwaking up at the same time every day can help regulate oubody's internal clock and make it easier to fall asleep andstay asleep.Additionally, creating a relaxing bedtime routitcan also help prepare our bodies and minds for sleep. It's alimportant to create a sleep-conducive environment. Thismeans making sure that our bedroomns are dark, cool andquiet. It also means avoiding the use of electronic devicessuch as phones and computers for at least an hour beforebedtimme, as the blue light emitted by these devices cansuppress melatonin production and make it harder to fallasleep. In conclusion, sleep is at essential aspect of ouroverall health and well-being. By establishing a consistent sleep schedule, creating a relaxing bedtime routine, andcreating a sleep-conducive environment we can ensure thatwe get the sleep we need to feel refreshed and energized.<br><br>阅读理解题目:<br>What are the effects of lack of sleep?<br>Why is it important to establish a consistent sleep schedule?<br>How can we create a sleep-conducive environmment?<br>请在阅读材料中找出答案.",
						time:'2023-01-19 22-53:39'
					},
					{
						title:"写一份大学物理实验报告",
						content:"实验题目:掌握热电偶测量温度的基本原理<br><br>实验目的:了解热电偶测量温度的原理和方法，并通过实验验证其精度。<br><br>实验设备: 热电偶、热电偶数据采集器、热源、加热器<br><br>实验步骤<br>准备热电偶和热电偶数据采集器。将热电偶接入数据采集器中。<br>使用加热器给热源加热，观察热电偶读数通过采集器记录热电偶在不同温度下的电压值。<br>根据热电偶的电压值和热电偶的温度系数计算出热电偶所测量的温度。比较实验测量的温度值和标准温度值之间的差距，确定热电偶的精度。<br><br>实验结果<br>通过实验，我们发现热电偶在测量温度时的精度很高其误差在+0.1C左右.<br><br>实验结论<br>热电偶是一种简单、可靠的温度测量方法，其精度高目可以测量的温度范围广。在工业和科学研究中都有广泛应用。",
						time:'2023-01-19 22-53:59'
					},
					{
						title:"应该清楚男友哪些方面才能嫁给他?",
						content:"在考虑嫁给男友之前，应该清楚他的哪些方面。首先应该考虑他的品德和性格。男友应该是一个诚实、正直、有责任感和尊重他人的人。他应该能够在生活中扮演一个信任和支持的角色。其次，应该考虑他的财务状况。婚姻是一种长期承诺，需要共同承担财务责任。应该确保男友有能力提供家庭所需的经济支持。第三，应该考虑他的家庭背景和文化价值观。这将影响到婚姻生活中的许多方面，包括家庭规则和习俗、教育子女的方式等。第四，应该考虑他的兴趣爱好和生活方式。应该确保两人的兴趣爱好和生活方式相似，以便在未来的生活中能够共同分享和享受。最后，应该考虑两人的感情。婚姻是一种爱情关系，应该确保彼此相爱并能够在未来的生活中共同成长。总而言之，在考虑嫁给男友之前，应该清楚他的品德和性格、财务状况、家庭背景和文化价值观、兴趣爱好和生活方式、以及两人的感情。仔细思",
						time:'2023-01-17 11:00:38'
					}
				]
			};
		},
		async onLoad() {
			// this.interstitialAdLoad()
			setTimeout(()=>{
				// this.interstitialAdClick()
			},2*1000)
		},
		onPageScroll(e) {
			this.pageScrollTop = e.scrollTop;
		},
		methods: {
			onSubmit() {
				uni.navigateTo({
					url: '/pages/main/answer/index'
				})
			},
			onClickContent(index){
				if(this.cIndex===index){
					this.cIndex = ''
				}else{
					this.cIndex = index
				}
				console.log(this.cIndex)
				this.$nextTick(()=>{
					this.getElementScollTop(index)
				})
			},
			getElementScollTop(index) {
				const query = uni.createSelectorQuery()
				query.select(`.panel${index}`).boundingClientRect((data) => {
					console.log(data, 'data')
					this.pageScrollTop = this.pageScrollTop + Math.round(data.top)
					uni.pageScrollTo({
						scrollTop: this.pageScrollTop, //滚动的距离
						duration: 500, //过渡时间
					})
				}).exec()
				
			},
			interstitialAdClick(){
				// 在适合的场景显示插屏广告
				if (interstitialAd) {
				  interstitialAd.show().catch((err) => {
				    console.error(err)
				  })
				}
			},
			interstitialAdLoad(){
				if (wx.createInterstitialAd) {
				  interstitialAd = wx.createInterstitialAd({
				    adUnitId: 'adunit-7fd77039475e7d2d'
				  })
				  interstitialAd.onLoad(() => {
					  console.log('onLoad')
				  })
				  interstitialAd.onError((err) => {
					  console.log('err')
				  })
				  interstitialAd.onClose(() => {
					  console.log('关闭')
				  })
				}
			},
		}
	}
</script>

<style lang="scss" scoped>
	/* 动画代码 */
	@keyframes example {
	  0%   {height: 114rpx;}
	  100% {height: 800rpx;}
	}
	.form {
		width: 90%;
		margin: 0 auto;
		z-index: 999;

		.header {
			margin-bottom: 30rpx;

			.title {
				text-align: center;
				color: #fff;
				margin: 30rpx 0rpx;
			}
		}

		.panel {
			padding: 30rpx;
			background-color: #fff;
			border-radius: 15rpx;
			box-shadow: 0rpx 10rpx 10rpx #eee;
			margin-bottom: 15rpx;
			.bottom{
				font-size: 24rpx;
			}
			.head {
				border-bottom: 1rpx solid #eee;
				padding-bottom: 30rpx;
				.title{
					font-weight: bolder;
					font-size: 30rpx;
				}
			}
			.content{
				margin: 30rpx 0rpx;
				height: 114rpx;
				display: -webkit-box;
			    overflow: hidden;
			    white-space: normal !important;
			    text-overflow: ellipsis;
			    word-wrap: break-word;
			    -webkit-line-clamp: 3;
				line-clamp: 3;
			    -webkit-box-orient: vertical;
			}
			.example{
				animation-name: example;
				animation-duration: 1s;
				position: relative;
				overflow: auto;
				text-overflow: inherit;
				-webkit-line-clamp: inherit;
				line-clamp: inherit;
				height: 800rpx;
			}
			.bottom{
				background-color: #F0FAF8;
				color: #26B3A0;
				padding: 15rpx;
				border-radius: 10rpx;
			}
		}
		.ad-box{
			margin: 20rpx 0;
		}
	}

	.bg {
		position: fixed;
		top: 0rpx;
		left: 0rpx;
		width: 100%;
		background-color: #26B3A0;
		min-height: 200rpx;
		border-radius: 0rpx 0rpx 140rpx 140rpx;
		z-index: -1;
	}
	
</style>
