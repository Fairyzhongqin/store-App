<template>
	<view>
		<view class="news-item" v-for="(item,index) in newsData" :key="index" @click="navigate(item.id)">
			<view class="img">
				<image :src="item.img"></image>
			</view>
			<view class="content">
				<view class="info">
					{{item.info}}
				</view>
				<view class="time_liulan">
					<text class="time">发布时间:{{item.time | formatDate}}</text>
					<text class="liulan">浏览人数: {{item.num}}</text>
				</view>
			</view>
		</view>
	</view>
	
</template>

<script>
	export default{
		props:['newsData'],
		filters:{
			formatDate(date) {
				const nDate = new Date(date)
				const year = nDate.getFullYear()
				const month = nDate.getMonth().toString().padStart(2,0)
				const day = nDate.getDay().toString().padStart(2,0)
				return year + '-' + month +'-'+ day
			}
		},
		data() {
			return {
				
			}
		},
		methods:{
			navigate(id) {
				this.$emit('goDetail',id)
			}
		}
	}
</script>

<style lang="scss">
	.news-item {
		display: flex;
		justify-content: space-between;
		width: 100%;
		height: 200rpx;
		border-bottom: 1px solid #aa0000;
		margin-bottom: 20rpx;
			.img {
				width: 270rpx;
				height: 100%;
				image {
					width: 100%;
					height: 100%;
				}
		}
		.content {
			width: 460rpx;
			display: flex;
			flex-direction: column;
			justify-content: space-between;
			.info {
				font-size: 30rpx;
				 display: -webkit-box;
				    overflow: hidden;
				    white-space: normal !important;
				    text-overflow: ellipsis;
				    word-wrap: break-word;
				    -webkit-line-clamp: 3;
				    -webkit-box-orient: vertical
			}
			.time_liulan {
				font-size: 20rpx;
				margin-bottom:10rpx;
				.liulan {
					margin-left: 20rpx;
					}
			}
		}
		
	}
</style>
