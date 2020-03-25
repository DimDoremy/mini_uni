<template>
	<view>
		<view class="uni-border-radius">
			<form @submit="calate">
				<view class="uni-form-font-size uni-border-radius">姓名</view>
				<input type="text" name="student" class="uni-input-border" />
				<view class="uni-form-font-size uni-border-radius">语文成绩</view>
				<input type="digit" name="chinese" class="uni-input-border" />
				<view class="uni-form-font-size uni-border-radius">数学成绩</view>
				<input type="digit" name="math" class="uni-input-border" />
				<view class="uni-form-font-size uni-border-radius">英语成绩</view>
				<input type="digit" name="english" class="uni-input-border" />
				<button form-type="submit" class="uni-border-radius">提交</button>
			</form>
		</view>
		<uni-card title="学生信息">
			<view> 姓名：{{student}} </view>
			<view> 语文：{{chinese}} </view>
			<view> 数学：{{math}} </view>
			<view> 英语：{{english}} </view>
			<view> 平均：{{average}} </view>
		</uni-card>
	</view>
</template>

<script>
export default {
	data() {
		return {
			student: 'Null',
			chinese: 0,
			math: 0,
			english: 0,
			average: 0,
			flag: true
		};
	},
	methods: {
		calate: function(e) {
			let err = false;
			let datas = e.detail.value;
			console.log(datas);
			if (datas.student == '' || datas.math == '' || datas.chinese == '' || datas.english == '') {
				uni.showToast({
					icon: 'none',
					title: '输入内容不能为空！',
					success() {
						err = true;
					}
				});
				if (err) {
					return;
				}
			} else if (datas.math * 1 == NaN || datas.chinese * 1 == NaN || datas.english * 1 == NaN) {
				uni.showToast({
					icon: 'none',
					title: '成绩不能输入数字之外的值！',
					success() {
						err = true;
					}
				});
				if (err) {
					return;
				}
			} else {
				this.student = datas.student;
				this.chinese = datas.chinese * 1;
				this.math = datas.math * 1;
				this.english = datas.english * 1;
				let avra = (datas.chinese * 1 + datas.math * 1 + datas.english * 1) / 3;
				this.average = avra;
				this.flag = false;
			}
			console.log(this.$data);
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
.uni-form-font-size {
	font-size: $uni-font-size-subtitle;
}
</style>
