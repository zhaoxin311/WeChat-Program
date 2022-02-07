<template>
	<view class="content">
		<view class="u-tag-con">
			<view class="u-page__tag-item" v-for="(item, index) in radios" :key="index" >
				<u-tag :text="item.name" :plain="!item.checked" type="primary" :name="index" 
				size="large" shape="circle" borderColor="#F1F3F5" :color="item.color" :bgColor="item.bgColor"
					@click="radioClick">
				</u-tag>
			</view>
		</view>
		<view class="u-page">
			<u-list
				scrollable
				showScrollbar="true"
				width="319px"
				height="580px"
				@scrolltolower="scrolltolower"
			>
				<u-list-item
					class="u-list-item-style"
					v-for="(item, index) in indexList"
					:key="index"
				>
					<view class="">
						<u-row customStyle="margin-bottom: 10px" @click="toPath(`/pages/detail/detail?productId=${item.productId}`)">
							<u-col span="5">
								<view class="view-left">
									<u-avatar
										class="avatar"
										slot="icon"
										shape="square"
										size="104"
										:src="item.url"
									></u-avatar>
								</view>
							</u-col>
							<u-col span="7">
								<view class="view-right" >
									<view style="font-size: 14px; font-weight: bold; color: rgba(51, 51, 51, 1);">{{item.title}}</view>
									<text class="con-text" style="font-size: 12px; color: rgba(51, 51, 51, 0.6); ">{{item.description}}</text>
									<u-rate count="5" v-model="item.star" activeColor="rgba(250, 176, 5, 1)" allowHalf="true"></u-rate>
								</view>
							</u-col>
						</u-row>
					</view>
				</u-list-item>
				<view class="other-title">
					为您推荐的其他产品
					
				</view>
			</u-list>
		</view>

	</view>
</template>

<script>
	export default {
		data() {
			return {
				radios: [{
						name:'全部',
						checked: true,
						color:'#ffffff',
						bgColor:'rgba(76, 110, 245, 1)'
					},
					{
						name:'向日葵',
						checked: false,
						color:'rgba(51, 51, 51, 0.7)',
						bgColor:'#F1F3F5'
					},
					{
						name:'仙人掌',
						checked: false,
						color:'rgba(51, 51, 51, 0.7)',
						bgColor:'#F1F3F5'
					},
					{
						name:'多肉',
						checked: false,
						color:'rgba(51, 51, 51, 0.7)',
						bgColor:'#F1F3F5'
					}
				],
				indexList: [
					{
						title:'多肉植物',
						productId:11,
						type:1,            //1:多肉；2:仙人掌；3:向日葵；
						url:'/static/plant1.png',
						description:'叶片一般都是很饱满的,并且株型也很紧并且株型也很紧凑并且株型也很紧凑并且株型也很紧凑并且株型也很紧凑并且株型也很紧凑并且株型也很紧凑凑,植株看起来是很小巧的...',
						star:5
					},
					{
						title:'仙人球',
						productId:21,
						type:2, 
						url:'/static/plant2.png',
						description:'叶片一般都是很饱满的,并且株型也很紧凑,植株看起来是很小巧的...',
						star:3.5
					},
					{
						title:'虎耳兰',
						productId:12,
						type:1, 
						url:'/static/plant3.png',
						description:'叶片一般都是很饱满的,并且株型也很紧凑,植株看起来是很小巧的...',
						star:4
					},
					{
						title:'仙人掌',
						productId:22,
						type:2, 
						url:'/static/plant4.png',
						description:'叶片一般都是很饱满的,并且株型也很紧凑,植株看起来是很小巧的...',
						star:2
					},
					{
						title:'向日葵',
						productId:31,
						type:3, 
						url:'/static/plant5.png',
						description:'叶片一般都是很饱满的,并且株型也很紧凑,植株看起来是很小巧的...',
						star:2
					},
					
				],
			}
		},
		onLoad() {},
		methods: {
			radioClick(name) {
				this.radios.map((item, index) => {
					item.checked = index === name ? true : false
					item.checked ? item.color="#fff" : item.color="rgba(51, 51, 51, 0.7)"
					item.checked ? item.bgColor="rgba(76, 110, 245, 1)" : item.bgColor="#F1F3F5"
				})
			},
			toPath(path) {
				console.log(path,'path')
				uni.navigateTo({
					url: path
				});
			},
		}
	}
</script>

<style lang="scss" scoped>
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		// border: 1px solid #2979FF;
		padding: 10px 10px 0 10px;
	}
	.u-tag-con{
		// margin-top: 20px;
		.u-page__tag-item {
			display: inline-block;
			margin: 7px;
			box-shadow: 6px 6px 12px -10px rgba(51, 51, 51, 0.7);
			border-radius: 50px;
		}
	}
	.view-left{
		width: 104px;
		height: 104px;
		margin: 20px 10px 20px 10px;
		// border: 1px solid red;
		.avatar{
			
			border-radius: 14px;
			overflow:hidden
		}
		border-radius: 14px;
	}
	.view-right{
		width: 167px;
		height: 92px;
		padding-left: 5px;
		margin-top: 5px;
		.con-text{
			margin: 5px 0px;
			display: -webkit-box;  //将对象作为弹性盒子模型展示 自适应布局
			-webkit-box-orient: vertical; //设置弹性盒子的子元素排列方式：从上到下垂直排列元素
			-webkit-line-clamp: 3; //显示文本的行数
			overflow: hidden; //超出的文本隐藏
		}
		// border: 1px solid #BEF5C8;
	}
	.other-title{
		font-size: 16px;
		color: rgba(51, 51, 51, 1);
		padding-left:5px ;
	}
	
	::v-deep{
		.u-border{
			border-style: none;
		}
		.u-list-item{
			width: 309px;
			height: 144px;
			margin: 5px;
			border-radius: 14px;
			flex-direction: initial;   //去掉下划线
			background-color: rgba(255, 255, 255, 1);
			box-shadow: 3px 3px 6px rgba(173, 174, 179, 0.09);
			border: 1px solid rgba(173, 174, 179, 0.09) ;
		}
		.u-cell__body{
			height: 144px;
		}
	}
</style>

