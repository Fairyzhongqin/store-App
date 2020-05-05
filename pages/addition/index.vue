<template>
	<view class="newsList">
		<news-list :newsData="newsData" @goDetail="goDetail"></news-list>
	</view>
</template>

<script>
	import newsList from '@/components/news-list/index.vue'
	export default{
		data() {
			return {
				newsData:[{
					img:'http://www.chinanews.com/2020/04-16/U855P4T8D9158656F107DT20200416131406.jpg',
					info:'疫情下，各路医生热血奋战，全国人民一起对抗疫情，共同抵抗，共创美好家园，要自律，你这个穷小子，千万不要将就，要相信自己是最棒的，未来永远是最好的，未来的你永远是最最好的，最最棒的，但是不努力永远只能想想',
					time:'2020.05.05',
					num:132,
					id:1
				},{
					img:'http://www.chinanews.com/2020/04-16/U855P4T8D9158656F107DT20200416131406.jpg',
					info:'疫情下，各路医生热血奋战，全国人民一起对抗疫情，共同抵抗，共创美好家园，要自律，你这个穷小子，千万不要将就，要相信自己是最棒的，未来永远是最好的，未来的你永远是最最好的，最最棒的，但是不努力永远只能想想',
					time:'2020.05.05',
					num:132,
					id:2
				},{
					img:'http://www.chinanews.com/2020/04-16/U855P4T8D9158656F107DT20200416131406.jpg',
					info:'疫情下，各路医生热血奋战，全国人民一起对抗疫情，共同抵抗，共创美好家园，要自律，你这个穷小子，千万不要将就，要相信自己是最棒的，未来永远是最好的，未来的你永远是最最好的，最最棒的，但是不努力永远只能想想',
					time:'2020.05.05',
					num:132,
					id:3
				},{
					img:'http://www.chinanews.com/2020/04-16/U855P4T8D9158656F107DT20200416131406.jpg',
					info:'疫情下，各路医生热血奋战，全国人民一起对抗疫情，共同抵抗，共创美好家园，要自律，你这个穷小子，千万不要将就，要相信自己是最棒的，未来永远是最好的，未来的你永远是最最好的，最最棒的，但是不努力永远只能想想',
					time:'2020.05.05',
					num:132,
					id:4
				},{
					img:'http://www.chinanews.com/2020/04-16/U855P4T8D9158656F107DT20200416131406.jpg',
					info:'疫情下，各路医生热血奋战，全国人民一起对抗疫情，共同抵抗，共创美好家园，要自律，你这个穷小子，千万不要将就，要相信自己是最棒的，未来永远是最好的，未来的你永远是最最好的，最最棒的，但是不努力永远只能想想',
					time:'2020.05.05',
					num:132,
					id:5
				},{
					img:'http://www.chinanews.com/2020/04-16/U855P4T8D9158656F107DT20200416131406.jpg',
					info:'疫情下，各路医生热血奋战，全国人民一起对抗疫情，共同抵抗，共创美好家园，要自律，你这个穷小子，千万不要将就，要相信自己是最棒的，未来永远是最好的，未来的你永远是最最好的，最最棒的，但是不努力永远只能想想',
					time:'2020.05.05',
					num:132,
					id:6
				}]
			}
		},
		methods:{
			goDetail(id) {
				console.log('出淤泥而不染')
				uni.navigateTo({
					url:'/pages/details/index?id='+id
				})
			}
		},
		components:{
			'news-list':newsList
		}
		
	}
</script>

<style lang="scss">
	.newsList {	
		
	}
</style>
