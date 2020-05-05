<template>
	<view class="detail">
		<scroll-view class="left" scroll-y>
			 <view :class="active == index ? 'active' : ''" v-for="(item,index) in cate" :key="index" @click="change(index)">鲜花酒水</view>
			
		</scroll-view> 
		<scroll-view class="right" scroll-y>
			<view v-for="(item,index) in cateGoods" :key="index" class="goods-item" >
				<image :src="item.img" @click="previewImg(index)"></image>
				<view>{{item.tit}}</view>
			</view>
			<view v-if="cateGoods.length === 0">暂无数据</view>
		</scroll-view>
	</view>
</template>

<script>
	export default{
		data() {
			return {
			cate:[{
				title:'鲜花酒水'
			},{
				title:'鲜花酒水'
			},{
				title:'鲜花酒水'
			},{
				title:'鲜花酒水'
			},{
				title:'鲜花酒水'
			},{
				title:'鲜花酒水'
			},{
				title:'鲜花酒水'
			},{
				title:'鲜花酒水'
			},{
				title:'鲜花酒水'
			},{
				title:'鲜花酒水'
			},{
				title:'鲜花酒水'
			},{
				title:'鲜花酒水'
			},{
				title:'鲜花酒水'
			},{
				title:'鲜花酒水'
			}],
				active:'0',
			cateGoods:[{
				img:'https://dss1.bdstatic.com/70cFvXSh_Q1YnxGkpoWK1HF6hhy/it/u=140840627,575902358&fm=26&gp=0.jpg',
				tit:'未来在自己手里 谁也阻拦不了'
			},{
				img:'https://dss3.bdstatic.com/70cFv8Sh_Q1YnxGkpoWK1HF6hhy/it/u=2534506313,1688529724&fm=26&gp=0.jpg',
				tit:'未来在自己手里 谁也阻拦不了'
			},{
				img:'https://dss0.bdstatic.com/70cFuHSh_Q1YnxGkpoWK1HF6hhy/it/u=1906469856,4113625838&fm=26&gp=0.jpg',
				tit:'未来在自己手里 谁也阻拦不了'
			}]
			}
		},
		methods:{
		async getCate() {
			const res = await this.$myRequest({
				url:'api/getCate?index='+1
			})	
			this.cate = res.data
			},
		async getGoods () {
			const res = await this.$myRequest({
				url:'api/getGoods?index='+id
			})
			this.cateGoods = res.data
		},
			change(index) {
				this.active = index
				this.getGoods()
			},
			previewImg(current) {
				const urls = this.cateGoods.map(item=> {
					return item.img
				})
				console.log(urls)
				uni.previewImage({
					urls,
					current
				})
			}
		},
		onLoad() {
			this.getCate()
		}
	}
</script>

<style lang="scss">
	page {
		height: 100%;
	}
	.detail{
		display: flex;
		height: 100%;
		
		.left{
			width: 200rpx;
			height: 100%;
			border-right: 1px solid #eee;
			view {
				width: 100%;
				height: 100rpx;
				line-height: 100rpx;
				text-align: center;
				border-top:1px solid #eee;
			}
			.active {
				background-color: rgb(170, 0, 0);
				color: #fff;
			}
		}
		.right {
			width: 520rpx;
			
			.goods-item{
				width: 100%;
				margin: 15rpx;
				border-radius: 15rpx;
				overflow: hidden;
				image {
					width: 100%;
				}
			}
			
		}
	}
</style>
