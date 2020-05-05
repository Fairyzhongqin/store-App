<template>
	<view class="details">
		<swiper indicator-dots circular>
			<swiper-item v-for="(item,index) in goodsDetails" :key="index">
				<image :src="item.src"></image>
			</swiper-item>
		</swiper>
		<uni-goods-nav :fill="true"  :options="options" :buttonGroup="buttonGroup"  @click="onClick" @buttonClick="buttonClick" />
	</view>
</template>

<script>
	import uniGoodsNav from '@/components/uni-goods-nav/uni-goods-nav.vue'

	export default{
		components: {uniGoodsNav},
		data() {
			return {
				id:'',
				goodsDetails:[{
					src:'../../static/imgs/bag.jpg'
				},{
					src:'../../static/imgs/forget.jpg'
				},{
					src:'../../static/imgs/friends.jpg'
				}],
				options: [{
				            icon: 'headphones',
				            text: '客服'
				        }, {
				            icon: 'shop',
				            text: '店铺',
				            info: 2,
				            infoBackgroundColor:'#007aff',
				            infoColor:"red"
				        }, {
				            icon: 'cart',
				            text: '购物车',
				            info: 2
				        }],
				    buttonGroup: [{
				          text: '加入购物车',
				          backgroundColor: '#ff0000',
				          color: '#fff'
				        },
				        {
				          text: '立即购买',
				          backgroundColor: '#ffa200',
				          color: '#fff'
				        }
				        ]
				      }
			
		},
		methods:{
		   async getGoodsDetails() {
				const res = await this.$myRequest({
					url:'api/mygoos?id='+this.id
				})
				this.goodsDetails = res.data
			},
			onClick (e) {
			        uni.showToast({
			          title: `点击${e.content.text}`,
			          icon: 'none'
			        })
			      },
			      buttonClick (e) {
			        console.log(e)
			        this.options[2].info++
			      }
			    },
		onLoad(options) {
			this.id = options.id
			this.getGoodsDetails()
		}
	}
</script>

<style lang="scss">
	.details{
		swiper{
			width: 750rpx;
			height: 700rpx;
			swiper-item {
				width: 100%;
				height: 100%;
				image {
					width: 100%;
					height: 100%;
				}
			}
			
		}
	}
</style>
