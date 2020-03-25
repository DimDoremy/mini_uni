<template>
	<view>
		<view class="uni-border-radius">
			<form @submit="calmax">
				<view class="uni-center-text uni-border-radius">求1到输入数之间所有偶数的和</view>
				<input type="digit" placeholder="请输入数字" name="num" class="uni-input-border" />
				<button form-type="submit" class="uni-border-radius">提交</button>
			</form>
			<uni-card title="计算结果">
				<text class="uni-output">{{ sum }}</text>
			</uni-card>
		</view>
	</view>
</template>

<script>
export default {
	data() {
		return {
			sum: 0
		};
	},
	methods: {
		calmax: function(e) {
			let sum = 0;
			let max = parseInt(e.detail.value['num']);
			console.log(max);
			for (var i = 1; i < max; i++) {
				if (i % 2 == 0) {
					sum = sum + i;
				}
			}
			this.sum = sum;
			console.log(sum);
		}
	}
};
</script>

<style lang="scss">
@import 'uni.scss';
.uni-border-radius {
	margin: $uni-border-radius-lg;
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
</style>
