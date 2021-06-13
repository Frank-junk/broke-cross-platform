<template>
  <view class="channel-page">
    <!-- 频道列表 -->
    <view class="channel-lists">
      <u-grid :col="2" :border="false" class="channel-lists_grid">
        <u-grid-item v-for="item in channelLists" :key="item.text">
          <u-avatar :src="item.image" size="60"></u-avatar>
          <view class="grid-text">{{ item.text }}</view>
        </u-grid-item>
      </u-grid>
    </view>
    <!-- 破产事务 -->
    <view class="channel-affairs"></view>
  </view>
</template>

<script>
  export default {
    data() {
      return {
        channelLists: [
          {
            image: '/static/images/home/zqsbtz.png',
            text: '债权申报通知',
          },
          {
            image: '/static/images/channel/ic_main_news.png',
            text: '消息提醒',
          },
        ],
      }
    },
  }
</script>

<style lang="scss" scoped>
  .channel-page {
    .channel-lists {
      width: 100%;
      height: 300rpx;
      padding: 0 32rpx;
      background-image: url('@/static/images/channel/icon_channel_top_bg.png');
      background-size: 100% 80%;
      background-repeat: no-repeat;
      position: relative;
      display: flex;
      align-items: flex-end;
      /deep/ .u-grid {
        border-radius: 12px;
      }
    }
  }
</style>
