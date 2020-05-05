<template>
	<view class="good-list">
		<view class="goods-item" v-for="(item,index) in goodsData" :key="index" @click="goGoodsDetail(item.id)">
			<image :src="item.img"></image>
			<view class="price">
				<text class="xianjia">￥{{item.nowPrice}}</text>
				<text class="yuanjia">￥{{item.beforePrice}}</text>
			</view>
			<view class="titName">
				{{item.name}}
			</view>
		</view>
		
		
		
	</view>
</template>

<script>
	export default{
		props:['goodsData'],
		methods:{
			goGoodsDetail(id){
					this.$emit('goGoodsDetails',id)
			}
		}
	}
</script>

<style lang="scss">
	.good-list {
		padding: 0 30rpx;
		display: flex;
		justify-content: space-between;
		flex-wrap: wrap;
		.goods-item {
			background-color: #fff;
			width:335rpx;
			height: 450rpx;
			margin-bottom: 30rpx;
			image {
				width: 100%;
				height: 300rpx;
			}
			.price {
				display: flex;
				justify-content: space-between;
				padding: 0 15rpx;
				.xianjia {
					color: #aa0000;
				}
				.yuanjia {
					color: #ccc;
					text-decoration: line-through;
				}
			}
		}
		
    }
</style>
