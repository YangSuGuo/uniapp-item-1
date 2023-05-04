<template>
    <view>
        <swiper
                :autoplay="true"
                :duration="1500"
                :indicator-dots="true"
                :interval="3000">
            <swiper-item v-for="item,index in swiperList" :key="index">
                <image :src="item.image" mode="scaleToFill"></image>
            </swiper-item>
        </swiper>

        <view class="icon">

            <view class="ige">
                <image mode="widthFix" src="../../static/link-02.png"></image>
            </view>
            <view class="ige">
                <image mode="widthFix" src="../../static/link-01.png"></image>
            </view>

        </view>

        <view class="grid-itst">

            <navigator v-for="item,index in gridList" :key="index" class="grid-item" url="/pages/shouye/shouye">
                <image :src="item.icon"></image>
                <text>{{ item.name }}</text>
            </navigator>

        </view>
    </view>
</template>
<script>
import {gridList, swiperList} from "@/commons/mock.js"

export default {
    data() {
        return {
            swiperList: swiperList,
            gridList: gridList
        }
    },
    methods: {},
}
</script>
<style>
swiper {
    height: 350rpx;
}

swiper image {
    width: 100%;
    height: 100%;
}

.icon {
    display: flex;
    justify-content: space-around;
    align-items: center;
    margin-top: 25rpx;
}

.ige {
    justify-content: center;
    width: 45%;
    height: 100%;
    display: flex;
}


.grid-itst {
    display: flex;
    flex-wrap: wrap;

}

.grid-item {
    width: 33.33%;
    height: 200rpx;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    box-sizing: border-box;
}

.grid-item image {
    width: 60rpx;
    height: 60rpx;

}

.grid-item text {
    font-size: 24rpx;
    margin-top: 10rpx;

}
</style>