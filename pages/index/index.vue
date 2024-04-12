<template>
	<view class="title">
		<h1>极韵AI</h1>

	</view>
	<swiper disable-touch :autoplay="true" :interval="2000" :duration="1000" vertical circular>
		<!-- 通知展示 -->
		<swiper-item v-for="tz in tongzhi">
			<view>{{tz}}</view>
		</swiper-item>

	</swiper>
	<scroll-view class="scroll" scroll-y>
		<!-- 消息展示 -->

		<view v-for="i in msgs">
			<view class="msgBox">

				{{ i }}

			</view>
		</view>
	</scroll-view>
	<view class="inputBox">
		<!-- 输入区 -->
		<input placeholder="请输入" v-model="input_text" :value="inputBoxText" style="width: 60%" class="input"
			type="text" />

		<el-button class="enterbtn" @click="addInputText()">
			发送
		</el-button>

	</view>

</template>

<script>
	export default {

		data() {
			return {
				msgs: ['这是一条测试消息'],
				tongzhi: [
					'By 极韵AI工作室',
					'这是前端测试内容',
					'没有接入后端',
					'有一个BUG',
					'按下发送按钮后输入框不会清空',
					'修不了了，就当这是特性',
					'doge',
					'制作人：fxbd5684',
					'制作人：百川byte',
					'感谢极韵AI顾问提供精神支持',

				] //在这里改通知的内容
			};
		},
		onLoad() {},
		methods: {
			addMsg(item) {
				this.msgs.push(item)
			},
			addInputText() {
				this.addMsg(this.input_text)
			}

		},
	};
</script>

<style lang="scss">
	body {
		background: linear-gradient(#42bdff, #c56bd6);
	}

	.title {
		text-align: center;
		font-size: 23px;
	}

	.scroll {
		height: 60vh;
		width: 100%;
		background-color: rgba(100, 100, 100, 0.5);

	}

	.msgBox {
		height: 25px;
		width: 95%;
		background-color: rgba(255, 255, 255, 0.8);
		border-radius: 2px;
		margin: 5px;



	}

	.inputBox {

		.input {
			margin-right: 10px;
			margin-left: 16px;
			margin-top: 12px;
			display: inline-block;
			border-style: solid;
			border-width: 1px;
			border-radius: 4px;
			height: 30px;
		}

		.enterbtn {
			border-radius: 4px;
			display: inline-block;
			margin-top: -25px;
			background-color: rgba(255, 255, 255, 0.3);
		}
	}

	swiper {
		height: 22px;
		width: 100%;
		background-color: rega(100, 100, 100, 0.5);
		border-style: solid;
		border-width: 1px;
		margin-bottom: 20px;
		margin-top: 12px;
	}
</style>