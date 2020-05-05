<template>
	<view class="zixundetail">
		<view class="tit">{{zixunData.tit}}</view>
		<view class="info">
			<rich-text :nodes="zixunData.info"></rich-text>
		</view>
		<view class="time">
			<text class="left">{{zixunData.reason}}</text>
			<text class="right">{{zixunData.time | formatDate}}</text>
		</view>
	</view>
</template>

<script>
	export default{
		data() {
			return {
				id:'',
				zixunData:{
					tit:'资讯',
					info:'2020-5-5,to do what you want to do ,<strong>来之不易才会珍惜</strong>，但是如果未来会很好，碰到的人也会很好，所以，</br>为自己拼一次，<text style="color:red">不管未来如何，你总是拼过的，</text>总能遇到，十年磨一剑，机会总是给努力的人，<br>中琴，你的实力撑不起你的野心，那么就好好努力，靠自己而不是别人。',
					reason:'彪悍的人生不需要解释',
					time:'2020.5.5'
				}
			}
		},
		methods:{
			async getzixunDetail() {
				const res = await this.$myRequest({
					url:'api/zixunDetail?index='+this.id
				})
			}
		},
		onLoad(options) {
			console.log(options.id)
			this.id = options.id
			this.getzixunDetail()
		}
	}
</script>

<style lang="scss">
	.zixundetail{
		padding: 0 15rpx;
		.tit {
			width: 750rpx;
			text-align: center;
			margin: 20rpx 0;
		}
		.info {
			font-size: 30rpx;
			text-indent: 60rpx;
		}
		.time {
			display: flex;
			justify-content: space-between;
			margin-top:10rpx;
		}
	}
</style>
