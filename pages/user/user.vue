<template>
	<view class="container">
		<view class="item">
			<u-col>
				<view class="layout_self">
					<u-avatar src="../../static/images/profile.jpg" size="60"></u-avatar>
					<view class="info">
						<text>昵称</text>
						<text>账号</text>
					</view>
				</view>
			</u-col>
		</view>
		
		
		<view class="item">
			<u-col >
				<view class="layout_buy">
					 <u-grid @click="click">
						<u-grid-item v-for="(baseListItem,baseListIndex) in baseList" :key="baseListIndex">
							<u-icon :customStyle="{paddingTop:20+'rpx'}" :name="baseListItem.name" :size="25"></u-icon>
								<text class="grid-text">{{baseListItem.title}}</text>
						</u-grid-item>
					</u-grid>
					<u-toast ref="uToast" />
				</view>
			</u-col>
		</view>
		
		<view class="item">
			<u-col>
				<view class="layout_set">
					<u-cell-group>
						<u-cell icon="star-fill" title="收藏"></u-cell>
						<u-cell icon="map-fill" title="地址"></u-cell>
						<u-cell icon="chat-fill" title="评价"></u-cell>
						<u-cell icon="setting-fill" title="设置"></u-cell>
					</u-cell-group>
				</view>
			</u-col>
		</view>
			
		<navBar :value="2"></navBar>
		
	</view>
</template>

<script>
	export default {
		data() {
			return {
				baseList: [{
					name: 'rmb-circle',
					title: '余额'
				},
				{
					name: 'order',
					title: '订单'
				},
				{
					name: 'clock',
					title: '浏览历史'
				}]
			};
		},
		methods:{
			click(name) {
				this.$refs.uToast.success(`点击了第${name}个`)
			}
		}
	}
</script>

<style lang="scss">
	.container{
		//background: #909399;
		.item{
			padding: 20rpx 30rpx;
			.layout_self{
				height: 180rpx;
				padding: 20rpx 50rpx;
				display: flex;
				align-items: center;
				border-radius: 10px;
				background: #fff;
				.info{
					padding-left: 40rpx;
					display: flex;
					flex-direction: column;
					
				}
			}
			.layout_buy {
				height:120rpx;
		        border-radius: 10px;
				background: #fff;
				padding: 10rpx 30rpx;
				.grid-text {
					font-size: 12px;
					padding: 10rpx 0rpx 10rpx 0rpx;
					/* #ifndef APP-PLUS */
					box-sizing: border-box;
					/* #endif */
				}
		    }
			.layout_set{
				height: 310rpx;
				border-radius: 10px;
				background: #fff;
				padding: 30rpx;
			}
			
		}
	}
	
</style>
