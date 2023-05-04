<template>
    <view>
        <view>
            <uni-search-bar
                    v-model="searchValue"
                    :focus="true"
                    cancelButton="none"
                    clearButton="auto"
                    @confirm="a">
            </uni-search-bar>

            <uni-section class="model2" title="商户分类" type="circle">
                <view class="example-info goods-sort">
                    <view class="tag-view">
                        <uni-tag circle="true" text="美食" type="success"></uni-tag>
                    </view>
                    <view class="tag-view">
                        <uni-tag circle="true" text="工作" type="primary"></uni-tag>
                    </view>

                    <view class="tag-view">
                        <uni-tag circle="true" text="无" type="warning"></uni-tag>
                    </view>

                    <view class="tag-view">
                        <uni-tag circle="true" text="小吃" type="error"></uni-tag>
                    </view>

                    <view class="tag-view">
                        <uni-tag circle="true" text="西餐" type="default"></uni-tag>
                    </view>
                </view>
            </uni-section>
            <uni-section title="商户" type="line">
                <view>
                    <uni-list v-for="item,index in foodList" :key="index">
                        <uni-list-item
                                :note="item.businessHours"
                                :thumb="item.images[0]"
                                :title="item.name"
                                link rightText="点击查看"
                                thumbSize="lg"
                                @click="dian('helo',item.comments)">
                        </uni-list-item>
                    </uni-list>
                </view>
            </uni-section>
        </view>
        <view>
            <uni-drawer ref="helo" :width="300" mode="left">
                <scroll-view class="scroll-view-box" scroll-y="true">
                    <view>
                        <uni-list v-for="item,index in message" :key="index">
                            <uni-card :extra="item.date" :title="item.name">
                                <text class="uni-body">
                                    {{ item.content }}
                                </text>
                                <uni-rate :value=zh(item.rating) class="rate-box" size="16">
                                </uni-rate>
                            </uni-card>
                        </uni-list>
                    </view>
                </scroll-view>
            </uni-drawer>
        </view>
    </view>
</template>

<script>
import {foodList} from '@/commons/mock.js'

export default {
    data() {
        return {
            searchValue: "",
            foodList: foodList,
            message: [],
        }
    },

    methods: {
        a: function () {
            console.log(this.searchValue)
            uni.showToast({
                title: "搜索中",
                duration: 1000,
                icon: "loading",
                // 成功回调函数
                success: function () {

                },
                // 失败
                fail: function () {

                },
                // 结束
                complete: function () {

                },

            })
        },
        dian(e, tmp_message) {
            this.$refs[e].open()
            this.message = [...tmp_message]
        },
        zh: function (ugly) {
            var i = ugly.length - 1
            var res = ugly.slice(0, i)
            res = parseInt(res)
            return res / 20
        },
    }
}
</script>

<style>
.goods-sort {
    display: flex;
    text-align: center;
}

.goods-sort view {
    flex: 0.2;
}

.scroll-view-box {
    flex: 1;
    position: absolute;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
}
</style>
