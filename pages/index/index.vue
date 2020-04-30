<template>
	<view class="home">
	    <swiper indicator-dots indicator-color="#ff5500" indicator-active-color="#ffff00" current="0" circular autoplay interval="1000">
	        <swiper-item>
	          <image src="@/static/imgs/bag.jpg"></image>
	        </swiper-item>   
			<swiper-item>
			<image src="@/static/imgs/forget.jpg"></image>
			</swiper-item> 
		    <swiper-item>
		     <image src="@/static/imgs/friends.jpg"></image>
		    </swiper-item>
			 <swiper-item>
			  <image src="@/static/imgs/fresh.svg"></image>
			 </swiper-item> 
		</swiper>
		<view class="nav">
			<view class="nav_item">
				<view class="iconfont "></view>
				<text>食品</text>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			}
		},
		onLoad() {
			this.getSwiper()
		},
		methods: {
			// getSwiper() {
			// 	uni.request({
			// 	    url: 'https://www.example.com/request', //仅为示例，并非真实接口地址。
			// 	    method:'get',
			// 	    success: (res) => {
			// 	        console.log(res.data);
			// 	    }
			// 	});
			// }
			// async getSwiper() {
			// const res = await uni.request({
			// 	    url: 'https://www.example.com/request', //仅为示例，并非真实接口地址
			// 	});
			// 	console.log(res)
			// }
			async getSwiper() {
				const res = await this.$myRequest({url:'/api/getlunbo'})
				console.log(res)
			}
			
		}
	}
</script>

<style lang="scss">
	.home {
		swiper {
			width: 750rpx;
			height: 375rpx;
			image {
				width: 100%;
				height: 100%;	
			}
		}
	}

</style>
