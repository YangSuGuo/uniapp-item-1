<template>
    <view>
        <uni-search-bar :focus="true" cancelButton="none" clearButton="auto" @confirm="a"></uni-search-bar>
        <uni-section class="mb-10" title="分类" type="square">
            <view class="example-info goods-sort">
                <view class="tag-view">
                    <uni-tag circle="true" text="推荐" type="success"></uni-tag>
                </view>

                <view class="tag-view">
                    <uni-tag circle="true" text="排行榜" type="primary"></uni-tag>
                </view>

                <view class="tag-view">
                    <uni-tag circle="true" text="视频" type="warning"></uni-tag>
                </view>

                <view class="tag-view">
                    <uni-tag circle="true" text="电台" type="error"></uni-tag>
                </view>

                <view class="tag-view">
                    <uni-tag circle="true" text="歌曲" type="default"></uni-tag>
                </view>
            </view>
        </uni-section>
        <uni-section sub-title="" title="推荐歌曲" type="line">
            <view>
                <uni-list>
                    <uni-list-item link note="晴天"
                                   rightText="点击查看"
                                   thumb="https://y.gtimg.cn/music/photo_new/T002R300x300M000003DFRzD192KKD.jpg"
                                   thumbSize="lg" title="周杰伦">
                    </uni-list-item>
                    <uni-list-item link note="majiko"
                                   rightText="点击查看"
                                   thumb="https://y.gtimg.cn/music/photo_new/T002R300x300M000003lkTOO3WLGUd.jpg"
                                   thumbSize="lg" title="狂おしいほど僕には美しい">
                    </uni-list-item>
                    <uni-list-item link note="prodby668"
                                   rightText="点击查看"
                                   thumb="https://p2.music.126.net/ZwWRyDt5YskAf5xp4MWn7g==/109951167128274929.jpg"
                                   thumbSize="lg" title="prolly my spookiest beat (SLOWED + REVERB)">
                    </uni-list-item>
                </uni-list>
            </view>
        </uni-section>
        <uni-section title="电台" type="line">
            <view>
                <uni-list>
                    <uni-list-item link note="まじ"
                                   rightText="点击查看"
                                   thumb="http://qpic.y.qq.com/music_cover/ql6nLQR4xWpJkbdkCFf2KgIZ9v3tIREX4KLEjkoFPCmCt46sqXiaMOQ/300?n=1" thumbSize=" medium" title="轻语电台|致那个回不去的夏天 关于夏日的记忆碎片 读听众留言">
                    </uni-list-item>
                    <uni-list-item link note="majiko"
                                   rightText="点击查看"
                                   thumb="http://d.musicapp.migu.cn/prod/playlist-service/playListimg/b23759b2-4ffb-4041-a825-57202cb19d82.jpg" thumbSize="lg" title="深夜电台故事】你长的好像一个人">
                    </uni-list-item>
                </uni-list>
            </view>
        </uni-section>
        <uni-section title="专辑" type="line">
            <view>
                <uni-list>
                    <uni-list-item link medium
                                   note="周杰伦"
                                   rightText="点击查看" thumb="https://y.gtimg.cn/music/photo_new/T002R300x300M000002Neh8l0uciQZ.jpg" thumbSize="lg" title="魔杰座">
                    </uni-list-item>
                </uni-list>
            </view>
        </uni-section>
    </view>
</template>

<script>
export default {
    data() {
        return {};
    }
}
</script>

<style lang="scss">
.goods-sort {
  display: flex;
  text-align: center;
}

.goods-sort view {
  flex: 0.2;
}
</style>
