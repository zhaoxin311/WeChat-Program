<template>
	<view class="">
		<u-tabbar
			:value="value1"
			@change="name => value1 = name"
			:fixed="true"
			:placeholder="true"
			activeColor="#82C91E"
			:safeAreaInsetBottom="true"
			zIndex=1
		>
			<u-tabbar-item text="首页" icon="home" name="home" @click="toPath(`/pages/index/index`)"  ></u-tabbar-item>
			<u-tabbar-item text="社区" icon="qzone" name="qzone"  @click="toPath(`/pages/community/index`)"></u-tabbar-item>
			<u-tabbar-item text="商场" icon="shopping-cart" name="shopping"  @click="toPath(`/pages/shopping/index`)"></u-tabbar-item>
		</u-tabbar>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				value1:'home',
				}
		},
		onLoad() {},
		methods: {
			toPath(path) {
				console.log(path,'path')
				uni.navigateTo({
					url: path
				});
			},
		}
	}
</script>

<style>
</style>
