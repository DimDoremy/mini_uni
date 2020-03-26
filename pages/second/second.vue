<template>
	<view>
		<uni-card title="计时器">
			<text>{{ Second }}</text>
		</uni-card>
		<view class="uni-flex">
			<button type="default" @click="timeCount" class="uni-border-radius">开始</button>
			<button type="default" @click="timeStop" class="uni-border-radius">停止</button>
			<button type="default" @click="timeReset" class="uni-border-radius">重置</button>
		</view>
	</view>
</template>

<script>
export default {
	data() {
		return {
			Second: Math.round(0.0 * 100) / 100,
			timer: 0
		};
	},
	methods: {
		timeCount: function() {
			this.timer = setInterval(() => {
				if (this.Second + 0.01 < 60) {
					this.Second = Math.round((this.Second + 0.01) * 100) / 100;
				} else {
					this.Second = Math.round(0.0 * 100) / 100;
				}
			}, 10);
		},
		timeStop: function() {
			clearInterval(this.timer);
		},
		timeReset: function() {
			clearInterval(this.timer);
			this.Second = Math.round(0.0 * 100) / 100;
		}
	}
};
</script>

<style lang="scss">
@import 'uni.scss';
.uni-border-radius {
	margin: $uni-border-radius-lg;
	-webkit-flex: 1;
	flex: 1;
}
.uni-input-border {
	border: 1px solid #007aff;
}
.uni-center-text {
	display: flex;
	justify-content: center;
	align-items: center;
	text-align: center;
	font-size: $uni-font-size-title;
}
.uni-time {
	text-align: center;
	font-size: 1.2cm;
}
.uni-flex {
	display: flex;
	flex-direction: row;
	-webkit-justify-content: center;
	justify-content: center;
}
</style>
