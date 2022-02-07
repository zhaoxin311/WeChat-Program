<template>
    <view>
        <u-grid
                :border="false"
				col="2"
        >
            <u-grid-item
                    v-for="(baseListItem,baseListIndex) in baseList"
                    :key="baseListIndex"
            >
			<view class="item">
		<!-- 		<u-icon
                    :customStyle="{paddingTop:20+'rpx'}"
                    :name="baseListItem.name"
                    :size="102"
                ></u-icon> -->
				<view style="margin: 12px;">
					<u--image :showLoading="true" :src="baseListItem.url"  shape="square" radius="12px" width="126px" height="123px" @click="click"></u--image>
					
				</view>
                <text class="grid-text">{{baseListItem.title}}</text>
				<view style="width: 126px; height: 32px; border-radius: 10px; margin: 12px; background-color:#82C91E ;" @click="click">
					 <u--text text="查看资料" color="white" size="12px" align="center" lineHeight="32px"></u--text>
				</view>
			</view>

            </u-grid-item>
        </u-grid>
        <u-toast ref="uToast" />
    </view>
</template>

<script>
    export default {
        data() {
            return {
                baseList: [{
						name: 'photo',
						url:'/static/plant1.png',
						title: '图片'
                    },
                    {
                        name: 'lock',
						url:'/static/plant2.png',
                        title: '锁头'
                    },
                    {
                        name: 'star',
						url:'/static/plant1.png',
                        title: '星星'
                    },{
						name: 'photo',
						url:'/static/plant1.png',
						title: '图片'
                    },
                    {
                        name: 'lock',
						url:'/static/plant1.png',
                        title: '锁头'
                    },
                    {
                        name: 'star',
						url:'/static/plant1.png',
                        title: '星星'
                    },{
						name: 'photo',
						url:'/static/plant1.png',
						title: '图片'
                    },
                    {
                        name: 'lock',
						url:'/static/plant1.png',
                        title: '锁头'
                    },
                    {
                        name: 'star',
						url:'/static/plant1.png',
                        title: '星星'
                    },
                ]
            }
        },
        methods: {
            click(name) {
                this.$refs.uToast.success(`点击了第${name}个`)
            }
        }
    }
</script>

<style lang="scss">
    .grid-text {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
        font-size: 14px;
        // color: #909399;
		color: rgba(51, 51, 51, 1);
        // padding: 10rpx 0 20rpx 0rpx;
        /* #ifndef APP-PLUS */
        box-sizing: border-box;
        /* #endif */
    }
	.item{
		width: 150px;
		height: 222px;
		margin: 5px;
		border: 1px solid rgba(173, 174, 179, 0.09) ;
		border-radius: 14px;
		background-color: rgba(255, 255, 255, 1);
		box-shadow: 3px 3px 6px rgba(173, 174, 179, 0.09);
	}
	::v-deep{
		// .u-grid-item{
		// 	width: 200px !important;
		// 	height: 144px;
		// 	// margin: 5px;
		// 	border-radius: 14px;
		// 	flex-direction: initial;   //去掉下划线
		// 	background-color: rgba(255, 255, 255, 1);
		// 	box-shadow: 3px 3px 6px rgba(173, 174, 179, 0.09);
		// 	border: 1px solid rgba(173, 174, 179, 0.09) ;
		// }
	}

</style>