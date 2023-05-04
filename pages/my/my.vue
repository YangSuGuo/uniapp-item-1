<template>
    <view>
        <view class="header-info">
            <image src="../../static/logo.png"></image>
        </view>

        <view>
            <uni-notice-bar :text="notice_msg" scrollable show-icon></uni-notice-bar>
        </view>

        <uni-section title="基本信息" type="circle">
            <uni-card :extra="sex" :sub-title="birthday" :thumbnail="avater" :title="nickname">
                <text class="uni-body">{{ my_word }}</text>
            </uni-card>
        </uni-section>

        <uni-section padding title="个性标签" type="circle">
            <view class="example-body">
                <view class="tag-view">
                    <uni-tag :inverted="true" text="中分" type="primary"/>
                </view>
                <view class="tag-view">
                    <uni-tag :inverted="true" text="唱" type="success"/>
                </view>
                <view class="tag-view">
                    <uni-tag :inverted="true" text="跳" type="warning"/>
                </view>
                <view class="tag-view">
                    <uni-tag :inverted="true" text="rap" type="error"/>
                </view>
                <view class="tag-view">
                    <uni-tag :inverted="true" text="篮球"/>
                </view>
            </view>
        </uni-section>

        <uni-section padding title="相关操作" type="circle">
            <uni-list>
                <uni-list-item link showArrow title="昵称修改" @click="inputDialogToggle"></uni-list-item>
                <uni-list-item link showArrow title="性别修改" @click="Si"></uni-list-item>
                <uni-list-item link showArrow title="个性签名" @click="mywordUpdate"></uni-list-item>
                <uni-list-item link showArrow title="手机号修改" @click="myphoneUpdate"></uni-list-item>
                <uni-list-item link showArrow title="分享名片" @click="mashareUpdate"></uni-list-item>
                <uni-list-item link showArrow title="注销" @click="userlongout"></uni-list-item>
            </uni-list>
        </uni-section>

        <view>
            <uni-popup ref="inputDialog" type="dialog">
                <uni-popup-dialog ref="inputClose" mode="input" placeholder="请输入内容" title="昵称修改"
                                  @confirm="dialogInputConfirm">
                </uni-popup-dialog>
            </uni-popup>
        </view>

        <view>
            <uni-popup ref="myword" type="dialog">
                <uni-popup-dialog ref="inputClose" mode="input" placeholder="请输入内容" title="个签修改"
                                  @confirm="mynewword">
                </uni-popup-dialog>
            </uni-popup>
        </view>

        <view>
            <uni-popup ref="pin" type="dialog">
                <uni-popup-dialog ref="inputClose" mode="input" placeholder="请输入内容" title="性别修改" @confirm="di">
                </uni-popup-dialog>
            </uni-popup>
        </view>

        <view>
            <uni-popup ref="myphone" type="dialog">
                <uni-popup-dialog cancelText="取消" confirmText="知道" content="暂不支持"
                                  mode="base"></uni-popup-dialog>
            </uni-popup>
        </view>

        <view>
            <uni-popup ref="myshare" type="dialog">
                <uni-popup-share></uni-popup-share>
            </uni-popup>
        </view>

        <view>
            <uni-popup ref="logout" type="dialog">
                <uni-popup-dialog cancelText="取消" confirmText="注销" content="确认注销" mode="base" title="注销"
                                  @confirm="afterLogout"></uni-popup-dialog>
            </uni-popup>
        </view>

    </view>
</template>

<script>
export default {
    data() {
        return {
            notice_msg: "滚动信息",
            nickname: "名字",
            avater: "../../static/avater.png",
            sex: "男",
            birthday: "1990-01-01",
            my_word: "签名",
        }
    },
    methods: {

        inputDialogToggle() {
            this.$refs.inputDialog.open()
        },
        dialogInputConfirm(val) {
            uni.showLoading({
                title: '修改中'
            })
            setTimeout(() => {
                uni.hideLoading()
                this.nickname = val
                this.$refs.inputDialog.close()
            }, 1000)
        },
        di(val) {
            uni.showLoading({
                title: '修改中'
            })
            setTimeout(() => {
                uni.hideLoading()
                this.sex = val
                this.$refs.pin.close()
            }, 1000)
        },
        Si: function () {
            this.$refs.pin.open()
        },
        mywordUpdate: function () {
            this.$refs.myword.open()
        },
        mynewword: function (val) {
            this.my_word = val
        },


        // 手机号
        myphoneUpdate: function () {
            this.$refs.myphone.open()
        },
        // 分享
        mashareUpdate: function () {
            this.$refs.myshare.open()
        },
        // 注销
        userlongout: function () {
            this.$refs.logout.open()
        },
        afterLogout: function () {
            this.nickname = " "
            uni.redirectTo({
                url: "/pages/Log/Log",
            })
        }
    }
}
</script>

<style>
.header-info {
    width: 100%;
    height: 350rpx;
    display: flex;
    justify-content: center;
    align-items: center;
    background: #2b4b6b;
}

.header-info image {
    display: block;
    border-radius: 50%;
    width: 150rpx;
    height: 150rpx;
}

.example-body view {
    display: inline-block;
    margin-left: 10rpx;
}
</style>
