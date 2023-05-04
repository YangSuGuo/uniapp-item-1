<template>
    <view>
        <view class="header_info">
            <text>登录</text>
        </view>
        <uni-section title="登录信息" type="line">
            <view class="example" style="padding: 15px; ">
                <uni-forms ref="form" :modelValue="formData">
                    <uni-forms-item label="账号" name="username" required>
                        <uni-easyinput v-model="formData.username" placeholder="请输入账号"></uni-easyinput>
                    </uni-forms-item>
                    <uni-forms-item label="密码" name="password" required>
                        <uni-easyinput
                                v-model="formData.password"
                                placeholder="请输入密码"
                                type="password">
                        </uni-easyinput>
                    </uni-forms-item>
                </uni-forms>
                <button type="primary" @click="submit">登录</button>
            </view>
        </uni-section>
    </view>
</template>

<script>
export default {
    data() {
        return {
            formData: {
                username: "root",
                password: "1234",
            }
        }
    },
    methods: {
        submit: function () {

            if (this.formData.username === "root" && this.formData.password === "1234") {
                uni.switchTab({
                    url: "/pages/index/index"
                })
            } else {
                uni.showModal({
                    title: "账号或密码错误"
                })
            }
        },

    }
}
</script>

<style>
.header_info {
    width: 100%;
    height: 200rpx;
    background-color: #2b4b6b;
    text-align: center;
}

.header_info text {
    font-size: 20px;
    line-height: 200rpx;
    color: white;
}
</style>
