<template>
	<view>
		<u-tabbar
			:value="value"
			:fixed="true"
			:placeholder="false"
			:safeAreaInsetBottom="false"
		>
			<u-tabbar-item text="首页" icon="home" @click="navClick" ></u-tabbar-item>
			<u-tabbar-item text="购物车" icon="shopping-cart" @click="navClick" ></u-tabbar-item>
			<u-tabbar-item text="我的" icon="account" @click="navClick" ></u-tabbar-item>
		</u-tabbar>
	</view>
</template>

<script>
	export default {
		name:"navBar",
		props:{
			value:{
				type:Number,
				default(){
					return 0
				}
			}
		},
		data() {
			return {
				
			};
		},
		methods:{
			navClick(e){
				if(e==0){
					uni.redirectTo({
						url:"/pages/index/index"
					})
				}
				if(e==1){
					uni.redirectTo({
						url:"/pages/cart/cart"
					})
				}
				if(e==2){
					uni.redirectTo({
						url:"/pages/user/user"
					})
				}
			}
		}
	}
</script>

<style lang="scss">

</style>