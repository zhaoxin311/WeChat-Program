<template>
    <view>
        <u-grid
                :border="false"
                @click="click"
        >
            <u-grid-item
                    v-for="(baseListItem,baseListIndex) in baseList"
                    :key="baseListIndex"
            >
                <u-icon
                        :customStyle="{paddingTop:20+'rpx'}"
                        :name="baseListItem.name"
                        :size="22"
                ></u-icon>
                <text class="grid-text">{{baseListItem.title}}</text>
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
                    title: '图片'
                    },
                    {
                        name: 'lock',
                        title: '锁头'
                    },
                    {
                        name: 'star',
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
        font-size: 14px;
        color: #909399;
        padding: 10rpx 0 20rpx 0rpx;
        /* #ifndef APP-PLUS */
        box-sizing: border-box;
        /* #endif */
    }
</style>