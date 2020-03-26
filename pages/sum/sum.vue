<template>
	<view>
		<table>
			<tr>
				<td><uni-number-box @change="change" :min="0" :max="99">1</uni-number-box></td>
				<td><uni-number-box @change="change" :min="0" :max="99">1</uni-number-box></td>
				<td><uni-number-box @change="change" :min="0" :max="99">1</uni-number-box></td>
			</tr>
			<tr>
				<td><uni-number-box @change="change" :min="0" :max="99">1</uni-number-box></td>
				<td><uni-number-box @change="change" :min="0" :max="99">1</uni-number-box></td>
				<td><uni-number-box @change="change" :min="0" :max="99">1</uni-number-box></td>
			</tr>
			<tr>
				<td><uni-number-box @change="change" :min="0" :max="99">1</uni-number-box></td>
				<td><uni-number-box @change="change" :min="0" :max="99">1</uni-number-box></td>
				<td><uni-number-box @change="change" :min="0" :max="99">1</uni-number-box></td>
			</tr>
			<tr>
				<td><uni-number-box @change="change" :min="0" :max="99">1</uni-number-box></td>
				<td><uni-number-box @change="change" :min="0" :max="99">1</uni-number-box></td>
				<td><uni-number-box @change="change" :min="0" :max="99">1</uni-number-box></td>
			</tr>
		</table>
		<view class="uni-border-radius">
			<button type="default">求和</button>
		</view>
	</view>
</template>

<script>
export default {
	data() {
		return {};
	},
	methods: {
		change: function(value) {}
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
