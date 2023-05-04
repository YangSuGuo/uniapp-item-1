<template>
    <view>
        <view v-for="item,index in foodList" :key="index" class="shop-itme">
            <view class="thumb">
                <image :src="item.images[0]"></image>
            </view>
            <view class="info">
                <text>{{ item.name }}</text>
                <text>电话: {{ splitPhone(item.phone) }}</text>
                <text>地址: {{ item.address }}</text>
                <text>营业时间: {{ item.businessHours }}</text>
            </view>
        </view>
    </view>
</template>

<script>
import {foodList} from '@/commons/mock.js'

export default {
    data() {
        return {
            foodList: foodList,
        }
    },
    methods: {
        splitPhone: function (phone) {
            if (phone.length !== 11) return phone
            var PHone = phone.split('')
            PHone.splice(3, 0, '-');
            PHone.splice(8, 0, '-');
            return PHone.join("");
        }
    }
}
</script>

<style>
.shop-itme {
    display: flex;
    padding: 15rpx;
    border: 1rpx solid #efefef;
    border-radius: 8rpx;
    box-shadow: 1rpx 1rpx 15rpx #ddd;
}

.thumb image {
    width: 250rpx;
    height: 250rpx;
    display: block;
    margin-right: 15rpx;
}

.info {
    display: flex;
    flex-direction: column;
    justify-content: space-around;
    font-size: 24rpx;
}
</style>

