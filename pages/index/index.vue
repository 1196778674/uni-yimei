<template>
	<view class="">
		<uni-search-bar-home @confirm="" @input="" />
		<view class="tags">
			<label class="tags-label">热搜:</label>
			<uni-tag text="标签" type="default" circle="true" inverted="true"></uni-tag>
			<uni-tag text="标签" type="default" circle="true" inverted="true"></uni-tag>
			<uni-tag text="标签" type="default" circle="true" inverted="true"></uni-tag>
			<uni-tag text="标签" type="default" circle="true" inverted="true"></uni-tag>
		</view>
		<swiper :indicator-dots="true" :autoplay="true" :interval="3000" :duration="1000" :circular="true">
			<swiper-item>
				<view class="swiper-item">
					<image style="width: 100%;" src="../../static/bg2.jpg" mode="widthFix"></image>
				</view>
			</swiper-item>
			<swiper-item>
				<view class="swiper-item">
					<image style="width: 100%;" src="../../static/bg4.jpg" mode="widthFix"></image>
				</view>
			</swiper-item>
		</swiper>
		<uni-grid class="grid-items" :column="5" :show-border="false"  :square="false">
		    <uni-grid-item v-for="(item,index) in list">
				<image @tap="goList(item)" class="grid-icons-item" src="../../static/bg2.jpg" mode=""></image>
		        <text class="text">{{item.name}}</text>
		    </uni-grid-item>
		</uni-grid>
	</view>
</template>

<script>
	import uniTag from "@/components/uni-tag/uni-tag.vue"
	import uniGrid from "@/components/uni-grid/uni-grid.vue"
	import uniGridItem from "@/components/uni-grid-item/uni-grid-item.vue"
	export default {
		data() {
			return {
				list: [{name: '超市', id: 0},{name: '电器', id: 1},{name: '服饰', id: 2},{name: '生鲜', id: 3},{name: '缴费', id: 4},{name: '拼单', id: 5},{name: '领券', id: 6},{name: '会员', id: 7},{name: '到家', id: 8},{name: '免息', id: 9}]
			}
		},
		components:{
			uniTag,
			uniGrid,
			uniGridItem
		},
		methods: {
			goList (obj) {
				uni.navigateTo({
					url: `../home/home?id=${obj.id}&name=${obj.name}`
				});
			}
		}
	}
</script>

<style>
	.uni-image{
		width: 100%;
	}
	.tags{
		display: flex;
		padding: 20upx;
		padding-top: 0;
	}
	.tags-label{
		line-height: 2rem;
		color: #333;
		font-size: 28upx;
	}
	.grid-items{
		margin-top: 30upx;
	}
	.uni-grid-item{
		text-align: center;
	}
	.grid-icons{
		margin: 0 auto;
	}
	.grid-icons-item{
		width: 55upx;
		height: 55upx;
		margin: 0 auto;
	}
	.uni-grid-item{
		margin-top: 25upx;
	}
</style>
