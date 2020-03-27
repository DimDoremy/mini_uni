<template>
	<view>
		<form @submit="submit" @reset="reset" class="uni-border-radius">
			<view class="" v-for="(item, index) in inputFormList" :key="index">
				<view class="uni-border-radius">
					<text class="uni-center-text">第 {{ index + 1 }} 个数字</text>
					<input type="number" v-model.number="item.number" class="uni-input-border" focus="true" />
				</view>
			</view>
			<view class="uni-flex">
				<button form-type="submit">提交</button>
				<button form-type="reset">重置</button>
				<button @click="add">添加</button>
				<button @click="del">删除</button>
				<button @click="clear">清空</button>
			</view>
			<button @click="homework" class="uni-border-radius">这是为了作业要求写的按钮</button>
		</form>
		<view class="uni-border-radius uni-center-text">
			<view>
				<text>输入数字和：{{ sum }}</text>
			</view>
			<view>
				<text>要求数字积：{{ mul }}</text>
			</view>
		</view>
	</view>
</template>

<script>
export default {
	data() {
		return {
			inputFormList: [
				{
					number: 0
				}
			],
			sum: 0,
			mul: 0
		};
	},
	methods: {
		submit: function(e) {
			this.sum = 0;
			this.mul = 1;
			for (let item of this.inputFormList) {
				this.sum += item.number;
				this.mul *= item.number;
			}
		},
		reset: function() {
			this.sum = 0;
			this.mul = 0;
			for (let item of this.inputFormList) {
				item.number = 0;
			}
		},
		add: function() {
			let addList = {
				number: 0
			};
			this.inputFormList.push(addList);
		},
		del: function() {
			if (this.inputFormList.length <= 1) {
				uni.showModal({
					title: '操作失败',
					content: '不能删除输入框到1个以下',
					showCancel: false
				});
				return;
			} else {
				this.inputFormList.pop();
			}
		},
		clear: function() {
			this.inputFormList = [
				{
					number: 0
				}
			];
		},
		homework: function() {
			if (this.inputFormList.length < 10) {
				uni.showModal({
					title: '个数不足',
					content: '必须有10个以上的数字',
					showCancel: false
				});
				return;
			}
			this.sum = 0;
			this.mul = 1;
			let count = 1;
			for (let item of this.inputFormList) {
				if (item.number >= 100) {
					uni.showModal({
						title: '输入错误',
						content: '输入的数字只能为最多两位的整数',
						showCancel: false
					});
					this.sum = 0;
					this.mul = 0;
					return;
				}
				this.sum += item.number;
				if (count <= 5) {
					this.mul *= item.number;
				}
				count++;
			}
		}
	}
};
</script>

<style lang="scss">
@import 'uni.scss';
.uni-border-radius {
	margin: $uni-border-radius-lg;
	-web-kit-flex: 1;
	flex: 1;
}
.uni-input-border {
	border: 1px solid #007aff;
}
.uni-center-text {
	text-align: center;
	font-size: $uni-font-size-title;
}
.uni-output {
	font-size: 1.2cm;
}
.uni-flex {
	display: flex;
	flex-direction: row;
	-webkit-justify-content: center;
	justify-content: center;
}
</style>
