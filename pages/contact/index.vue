<template>
	<view class="contact">
		<image src="https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1588595926613&di=72906124e1816e534e07f40e108dde80&imgtype=0&src=http%3A%2F%2Fqcloud.dpfile.com%2Fpc%2FDzO6otm-Tzcf8bvq9SjS7m2J3LjAHx6VNL248IPAyGaViAhwi3EnjQ1hCPpfw-X0TYGVDmosZWTLal1WbWRW3A.jpg"></image>
		<view class="info">
			<view class="phone-contact" @click="phoneCall">联系电话: 1230 90287339</view>
			<view class="address">地址：江苏省南京市江宁区121号</view>
		</view>
		<map name="" class="map" :longitude="longitude" :latitude="latitude" :markers="markers" :scale="scale"></map>
	</view>
</template>

<script>
	export default{
		data() {
			return {
					longitude:118.84002,
					latitude:31.95266,
					scale:11,
					markers:[{
						longitude:118.84002,
						latitude:31.95266,
						iconPath:'/static/logo.png',
						callout:{
							content:'这是江宁区图书馆',
							color:'red',
							borderRadius:10,
							bgColor:'green'
						},
						label:{
							content:'要越来越好',
							color:'yellow'
						}
					}]
			}
		},
		methods:{
			phoneCall() {
				uni.makePhoneCall({
				    phoneNumber: '15715577026' //仅为示例
				});
			}
		}
	}
</script>

<style lang="scss">
	.contact {
		image {
			width: 100%;
		}
		.phone-contact {
			margin-top:10rpx;
			height: 50rpx;
			line-height: 50rpx;
		}
		.address {
			margin-top:10rpx;
			height: 50rpx;
			line-height: 50rpx;
		}
		.map {
			width: 100%;
			margin-top:30rpx;
			height: 750rpx;
		}
		}
</style>
