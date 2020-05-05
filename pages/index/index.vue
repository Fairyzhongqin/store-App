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
			<view class="nav_item" v-for="(item,index) in navData" :key="index" @click="getNavigate(item.path)">
				<view :class="item.icon"></view>
				<text>{{item.title}}</text>
			</view>
		
		</view>
		<navigator url="../contact/index" class="lianxi">联系我们</navigator>
		<view class="hot-goods">
			<view class="recommend">推荐商品</view>
		   <goods-list :goodsData="goodsData" @goGoodsDetails="goGoodsDetails"></goods-list>
		</view>
		<view v-if="flag">已经到底了，再见了，追寻自己的梦了</view>
	</view>
</template>

<script>
	import goodsList from '@/components/goods-list/index.vue'
	export default {
		data() {
			return {
				pageIndex:1,
				flag: false,
				navData:[{
					icon:'iconfont icon-shipin',
					title:'食品',
					path:'/pages/goods/index',
					id:1
				},{
					icon:'iconfont icon-fushi',
					title:'服饰',
					path:'pages/news/index',
					id:2
				},{
					icon:'iconfont icon-meizhuang',
					title:'美妆',
					path:'pages/news/index',
					id:3
				},{
					icon:'iconfont icon-yundong',
					title:'运动',
					path:'pages/news/index',
					id:4
				}],
				goodsData:[{
					img:'https://img.alicdn.com/imgextra/i1/124753390/O1CN01pzwH7n1aufGDA7Eqy_!!0-saturn_solar.jpg_220x220.jpg_.webp',
					nowPrice:2324,
					beforePrice:34335,
					name:'春季新品 网红产品 气质仙女风',
					id:1
				},{
					img:'https://img.alicdn.com/imgextra/i1/124753390/O1CN01pzwH7n1aufGDA7Eqy_!!0-saturn_solar.jpg_220x220.jpg_.webp',
					nowPrice:2324,
					beforePrice:34335,
					name:'春季新品 网红产品 气质仙女风',
					id:2
				},{
					img:'https://img.alicdn.com/imgextra/i1/124753390/O1CN01pzwH7n1aufGDA7Eqy_!!0-saturn_solar.jpg_220x220.jpg_.webp',
					nowPrice:2324,
					beforePrice:34335,
					name:'春季新品 网红产品 气质仙女风',
					id:3
				},{
					img:'https://img.alicdn.com/imgextra/i1/124753390/O1CN01pzwH7n1aufGDA7Eqy_!!0-saturn_solar.jpg_220x220.jpg_.webp',
					nowPrice:2324,
					beforePrice:34335,
					name:'春季新品 网红产品 气质仙女风',
					id:4
				},{
					img:'https://img.alicdn.com/imgextra/i1/124753390/O1CN01pzwH7n1aufGDA7Eqy_!!0-saturn_solar.jpg_220x220.jpg_.webp',
					nowPrice:2324,
					beforePrice:34335,
					name:'春季新品 网红产品 气质仙女风',
					id:5
				}]
			}
		},
		onLoad() {
			this.getSwiper()
			this.getGoods()
		},
		onReachBottom() {
			// console.log('姜超')
			// if(this.goodsData.length < this.pageIndex * 10) return this.flag = true
			// this.pageIndex++
			// this.getGoods()
		},
		components:{
			'goods-list':goodsList
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
			},
			async getGoods() {
				const res = await this.$myRequest(
				 {url:'/api/getGoods?pageIndex='+this.pageIndex}
				)
				// this.goodsData = [...this.goodsData,...res.data.message] 以免数据没渲染
			},
			getNavigate(url) {
				uni.navigateTo({
					url
				})
			},
			goGoodsDetails(id) {
				uni.navigateTo({
					url:'/pages/goodsDetails/index?id='+id
				})
			}
			
		},
		
	}
</script>

<style lang="scss">
	.home {
		background-color: #eee;
		swiper {
			width: 750rpx;
			height: 375rpx;
			image {
				width: 100%;
				height: 100%;	
			}
		}
		.nav {
			display:flex;	
			background-color: #fff;
			.nav_item {
				flex:1;
				text-align: center;
				margin: 20rpx 0;
				.iconfont {
					width: 100rpx;
					height: 100rpx;
					background-color: #aa0000;
					font-size: 50rpx;
					text-align: center;
					line-height: 100rpx;
					color: #fff;
					margin: 0 auto;
					border-radius: 50%;
					margin-bottom: 10rpx;
				}
			}
			
		}
		.lianxi {
			width: 100%;
			height: 100rpx;
			text-align: center;
			line-height: 100rpx;
			margin: 10rpx 0;
			background-color: #fff;
			border: 1px solid transparent;
		}
		.hot-goods {
			background-color: #eee;
			overflow: hidden;
			.recommend {
				height: 100rpx;
				background-color: #fff;
				margin: 20rpx 0;
				text-align: center;
				line-height: 100rpx;
				letter-spacing: 30rpx;
				color: #aa0000;
			}
			
	}
	}

</style>
