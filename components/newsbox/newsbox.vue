<template>
	<view class="newsbox">
		<view class="pic">
			<image :src="item.picurl" mode="aspectFill"></image>
		</view>
		
		<view class="text">
			<view class="title">{{item.title}}</view>
			<view class="info" v-if="!item.looktime">
				<view class="font">{{item.author}}</view>
				<view class="font">{{item.hits}}浏览</view>
			</view>		
			<view class="info" v-else>
				<view>浏览时间{{item.looktime}}</view>

			</view>
		</view>
	</view>
</template>

<script>
	export default {
		name:"newsbox",
		props:{
			item:{
				type: Object,
				default(){
					return {
						title: "组件内默认的标题",
						author: "张三",
						hits: 668,
						picture: "../../static/images/nopic.jpg"
						}
				}
			}
		},
		data() {
			return {
				
			};
		}
	}
</script>

<style lang="scss">
.newsbox {
	display: flex;
	justify-content: space-between;
	.pic {
		width: 230rpx;
		height: 160rpx;
		image {
			width: 100%;
			height: 100%;
		}
	}
	.text {
		flex: 1;
		padding-left: 20rpx;
		display: flex;
		flex-direction: column;
		justify-content: space-between;
		.title {
			font-size: 36 rpx;
			color: #333;
			display: -webkit-box;
			overflow: hidden;
			text-overflow: ellipsis;
			-webkit-line-clamp: 2;
			-webkit-box-orient: vertical;
		}
		.info {
			font-size: 26rpx;
			color: #999;
			display: flex;
			.font {
				padding-right: 20rpx;
			}
		}
	}
}
</style>