<template>
	<scroll-view class="scroll" scroll-y>
		<!-- 消息展示 -->

		<view v-for="i in msgs">
			<view class="msgBox">

				{{ i }}

			</view>
		</view>
	</scroll-view>

	<view class="line"></view>

	<view class="inputBox">
		<!-- 输入区 -->
		<input>
		<textarea placeholder="请输入" v-model="input_text" :value="inputBoxText" style="width: 100%" class="input"
			type="text">
			</textarea>

		<button class="enterbtn" @click="addInputText()">
			发送
		</button>

	</view>

</template>

<script>
	export default {

		data() {
			return {
				msgs: ['这是一条测试消息'],

			};
		},
		onLoad() {},
		methods: {
			addMsg(item) {
				this.msgs.unshift(item)
			},
			addInputText() {
				this.addMsg(this.input_text)
			}

		},
	};
</script>

<style lang="scss">
	body {
		background: rgb(59, 59, 59);
	}

	.line {
		margin-top: 1vh;
		width: 100%;
		border-top: solid #9eb1c6 1px;
	}


	.scroll {
		bottom: 0;
		height: 60vh;
		width: 100%;
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

			background-color: rgba(255, 255, 255, 0.4);
			color: #eeffeb;
			height:24vh;

		}

		.enterbtn {
			background-color: rgba(159, 170, 170, 0.8);
			
		}
	}
</style>