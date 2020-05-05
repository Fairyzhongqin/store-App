<template>
	<view>
		<goods-list :goodsData="goodsData" @goGoodsDetails="goGoodsDetails"></goods-list>
	</view>
</template>

<script>
	import goodsList from '@/components/goods-list/index.vue'
	export default {
		data() {
			return {
				goodsData:[{
					img:'https://img.alicdn.com/imgextra/i1/124753390/O1CN01pzwH7n1aufGDA7Eqy_!!0-saturn_solar.jpg_220x220.jpg_.webp',
					nowPrice:2324,
					beforePrice:34335,
					name:'春季新品 网红产品 气质仙女风'
				},{
					img:'https://img.alicdn.com/imgextra/i1/124753390/O1CN01pzwH7n1aufGDA7Eqy_!!0-saturn_solar.jpg_220x220.jpg_.webp',
					nowPrice:2324,
					beforePrice:34335,
					name:'春季新品 网红产品 气质仙女风'
				},{
					img:'https://img.alicdn.com/imgextra/i1/124753390/O1CN01pzwH7n1aufGDA7Eqy_!!0-saturn_solar.jpg_220x220.jpg_.webp',
					nowPrice:2324,
					beforePrice:34335,
					name:'春季新品 网红产品 气质仙女风'
				},{
					img:'https://img.alicdn.com/imgextra/i1/124753390/O1CN01pzwH7n1aufGDA7Eqy_!!0-saturn_solar.jpg_220x220.jpg_.webp',
					nowPrice:2324,
					beforePrice:34335,
					name:'春季新品 网红产品 气质仙女风'
				},{
					img:'https://img.alicdn.com/imgextra/i1/124753390/O1CN01pzwH7n1aufGDA7Eqy_!!0-saturn_solar.jpg_220x220.jpg_.webp',
					nowPrice:2324,
					beforePrice:34335,
					name:'春季新品 网红产品 气质仙女风'
				},{
					img:'https://img.alicdn.com/imgextra/i1/124753390/O1CN01pzwH7n1aufGDA7Eqy_!!0-saturn_solar.jpg_220x220.jpg_.webp',
					nowPrice:2324,
					beforePrice:34335,
					name:'春季新品 网红产品 气质仙女风'
				},{
					img:'https://img.alicdn.com/imgextra/i1/124753390/O1CN01pzwH7n1aufGDA7Eqy_!!0-saturn_solar.jpg_220x220.jpg_.webp',
					nowPrice:2324,
					beforePrice:34335,
					name:'春季新品 网红产品 气质仙女风'
				},{
					img:'https://img.alicdn.com/imgextra/i1/124753390/O1CN01pzwH7n1aufGDA7Eqy_!!0-saturn_solar.jpg_220x220.jpg_.webp',
					nowPrice:2324,
					beforePrice:34335,
					name:'春季新品 网红产品 气质仙女风'
				},{
					img:'https://img.alicdn.com/imgextra/i1/124753390/O1CN01pzwH7n1aufGDA7Eqy_!!0-saturn_solar.jpg_220x220.jpg_.webp',
					nowPrice:2324,
					beforePrice:34335,
					name:'春季新品 网红产品 气质仙女风'
				},{
					img:'https://img.alicdn.com/imgextra/i1/124753390/O1CN01pzwH7n1aufGDA7Eqy_!!0-saturn_solar.jpg_220x220.jpg_.webp',
					nowPrice:2324,
					beforePrice:34335,
					name:'春季新品 网红产品 气质仙女风'
				},{
					img:'https://img.alicdn.com/imgextra/i1/124753390/O1CN01pzwH7n1aufGDA7Eqy_!!0-saturn_solar.jpg_220x220.jpg_.webp',
					nowPrice:2324,
					beforePrice:34335,
					name:'春季新品 网红产品 气质仙女风'
				}]
			}
		},
		components:{
			'goods-list':goodsList
		},
		// onPullDownRefresh () {
		// 	this.pageIndex = 1
		// 	this.goodsData = []
		// 	this.getGoods(()=> {
		// 		uni.stopPullDownRefresh()
		// 	})
		// },
		methods: {
			// getGoods(callback) {
			// 	const res = this.$myRequest({
			// 		url:"api/goodsList/pageIndex?="+this.pageIndex
			// 	})
			// 	this.goodsData = [...this.goodsData,...res.data.message]
			// 	callback && callback()
			// }
			goGoodsDetails(id) {
				uni.navigateTo({
					url:'/pages/goodsDetails/index?id='+id
				})
			}
		}
	}
</script>

<style>

</style>
