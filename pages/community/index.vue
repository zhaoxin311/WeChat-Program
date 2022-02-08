<template>
	<u-list
		@scrolltolower="scrolltolower"
	>
		<u-list-item
			v-for="(item, index) in cardList"
			:key="index"
		>
		<view class="card-item">
			<view style="height: 36px;margin-bottom: 5px;  display: flex; justify-content: left;">
				<u-avatar  :src="item.avatar" shape="circle" size="36px"  />
				<view class="flex-col  group-name">
					<text class="text-name">{{item.name}}</text>
					<text class="text-time">{{item.time}}分钟前</text>
				</view>
			</view>
			<u--image :showLoading="true" :src="item.image" width="319px" height="166px" ></u--image>
			<view class="card-item-title" style="font-size: 14px; margin: 10px 0;">{{item.title}}</view>
			<view class="flex-row " style="width: 319px; height: 24px;">
				<view class="flex-row ">
					<u--image :showLoading="true" src="/static/eye.png" width="18px" height="18px" ></u--image>
					<text class="bottom-number">{{item.num1}}</text>
				</view>
				<view class="flex-row " style="margin-left: 40px;">
					<u--image :showLoading="true" src="/static/pinglun.png" width="18px" height="18px" ></u--image>
					<text class="bottom-number" >{{item.num2}}</text>
				</view>
				<view class="flex-row " style="margin-left: 40px;">
					<u--image :showLoading="true" src="/static/zhuanfa.png" width="18px" height="18px" ></u--image>
					<text class="bottom-number">{{item.num3}}</text>
				</view>
				<view class="flex-row"style="margin-left:80px;" >
					<u--image :showLoading="true" src="/static/heart1.png" width="18px" height="18px" ></u--image>
					<text class="bottom-number">{{item.num4}}</text>
				</view>
			</view>

		</view>
		</u-list-item>
	</u-list>
</template>

<script>
    export default {
        data() {
            return {
				cardList:[{
					id:1,
					avatar:'/static/plant5.png',
					name:'方恩与',
					time:12,
					image:'/static/swiper3.png',
					title:'下面我们会从不同维度来分析一下我们会从不同维度来分析一下我们会从不同维度来分析一下我们会从不同维度来分析一下',
					num1:21,
					num2:22,
					num3:78,
					num4:321,
				},{
					id:2,
					avatar:'/static/plant1.png',
					name:'方恩与',
					time:12,
					image:'/static/swiper2.png',
					title:'作为用户和产品之间的桥梁，社交分享我们会从不同维度来分析一下在产品的...',
					num1:21,
					num2:22,
					num3:78,
					num4:321,
				},{
					id:3,
					avatar:'/static/plant2.png',
					name:'方恩与',
					time:12,
					image:'/static/swiper3.png',
					title:'下面我们会从不同维度来分析一下',
					num1:21,
					num2:22,
					num3:78,
					num4:321,
				},{
					id:4,
					avatar:'/static/plant3.png',
					name:'方恩与',
					time:22,
					image:'/static/swiper1.png',
					title:'下面我们会从不同维度来分析一下',
					num1:41,
					num2:253,
					num3:43,
					num4:321,
				},
				]
            }
        },
        methods: {
        }
    }
</script>

<style lang="scss">
	.card-item{
		width: 319px;
		height: 276px;
		margin: 10px auto;
		border-bottom: 1px solid #929292;
		.card-item-title{
			  overflow: hidden;
			  text-overflow:ellipsis;
			  white-space: nowrap;
		}
	}
  .group-name {
	margin-left: 5px;
    .text-name {
      color: rgb(0, 0, 0);
      font-size: 14px;
      line-height: 13px;
	  margin-top: 5px;
    }
    .text-time {
      margin-top: 3px;
      color: #707070;
      font-size: 10px;
      font-weight: 700;
    }
  }
  .bottom-number{
	  font-size: 12px; 
	  color: #7a7a7a;
	  line-height: 18px;
	  margin-left: 5px;
  }
  .items-center {
    display: flex;
    align-items: center;
  }
  .flex-col {
    display: flex;
    flex-direction: column;
  }
  .flex-row {
    display: flex;
    flex-direction: row;
  }
</style>