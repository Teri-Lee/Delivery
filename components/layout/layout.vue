<template>
	<view class="item">
		<u-col >
			<view class="layout" :style="{height:height+'rpx'}"></view>
		</u-col>
	</view>
</template>

<script>
	export default {
		name:"layout",
		props:{
			height:{
				type:Number,
				default(){
					return 45
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
	.item{
		padding: 40rpx;
		.layout {
	        border-radius: 10px;
			background: #e5e9f2;
	    }
	}
</style>