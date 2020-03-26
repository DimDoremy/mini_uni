<template>
	<view class="uni-border-radius">
		<navigator url="../ifelse/ifelse" class="uni-border-radius"><button type="default">选择分支结构</button></navigator>
		<navigator url="../loop/loop" class="uni-border-radius"><button type="default">循环结构</button></navigator>
		<navigator url="../sum/sum" class="uni-border-radius"><button type="default">计算和</button></navigator>
		<navigator url="../second/second" class="uni-border-radius"><button type="default">计时器</button></navigator>
	</view>
</template>

<script>
export default {
	data() {
		return {};
	},
	methods: {}
};
</script>

<style lang="scss">
@import 'uni.scss';
.uni-border-radius {
	margin: $uni-border-radius-lg;
}
</style>
