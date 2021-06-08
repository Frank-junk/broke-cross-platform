<template>
  <div class="home-page">
    <view class="home-swiper">
      <u-swiper :list="swiperList" height="260rpx"></u-swiper>
    </view>
    <view class="home-feats">
      <u-grid :col="4" :border="false">
        <u-grid-item v-for="item in featLists" :key="item.text">
          <u-avatar :src="item.image" size="60"></u-avatar>
          <view class="grid-text">{{ item.text }}</view>
        </u-grid-item>
      </u-grid>
    </view>
    <view class="creditor-container">
      <view class="title_bar">
        <view class="name">债权申报通知</view>
        <view>
          <text class="more">更多</text>
          <u-icon name="arrow-right"></u-icon>
        </view>
      </view>
      <view class="creditor_lists">
        <u-time-line>
          <u-time-line-item nodeTop="2">
            <!-- 此处自定义了左边内容，用一个图标替代 -->
            <template v-slot:node>
              <view class="u-node" style="background: #19be6b">
                <!-- 此处为uView的icon组件 -->
                <u-icon name="pushpin-fill" color="#fff" :size="24"></u-icon>
              </view>
            </template>
            <template v-slot:content>
              <view>
                <view class="u-order-title">待取件</view>
                <view class="u-order-desc">
                  [自提柜]您的快件已放在楼下侧门，直走前方53.6米，左拐约10步，再右拐直走，见一红灯笼停下，叩门三下，喊“芝麻开门”即可。
                </view>
                <view class="u-order-time">2019-05-08 12:12</view>
              </view>
            </template>
          </u-time-line-item>
          <u-time-line-item>
            <!-- 此处没有自定义左边的内容，会默认显示一个点 -->
            <template v-slot:content>
              <view>
                <view class="u-order-desc">
                  【深圳市】日照香炉生紫烟，遥看瀑布挂前川，飞流直下三千尺，疑是银河落九天。
                </view>
                <view class="u-order-time">2019-12-06 22:30</view>
              </view>
            </template>
          </u-time-line-item>
          <u-time-line-item>
            <!-- 此处没有自定义左边的内容，会默认显示一个点 -->
            <template v-slot:content>
              <view>
                <view class="u-order-desc">
                  【深圳市】日照香炉生紫烟，遥看瀑布挂前川，飞流直下三千尺，疑是银河落九天。
                </view>
                <view class="u-order-time">2019-12-06 22:30</view>
              </view>
            </template>
          </u-time-line-item>
          <u-time-line-item>
            <!-- 此处没有自定义左边的内容，会默认显示一个点 -->
            <template v-slot:content>
              <view>
                <view class="u-order-desc">
                  【深圳市】日照香炉生紫烟，遥看瀑布挂前川，飞流直下三千尺，疑是银河落九天。
                </view>
                <view class="u-order-time">2019-12-06 22:30</view>
              </view>
            </template>
          </u-time-line-item>
          <u-time-line-item>
            <!-- 此处没有自定义左边的内容，会默认显示一个点 -->
            <template v-slot:content>
              <view>
                <view class="u-order-desc">
                  【深圳市】日照香炉生紫烟，遥看瀑布挂前川，飞流直下三千尺，疑是银河落九天。
                </view>
                <view class="u-order-time">2019-12-06 22:30</view>
              </view>
            </template>
          </u-time-line-item>
        </u-time-line>
      </view>
    </view>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        swiperList: [
          {
            image: '/static/images/new/main_home_show_banner.png',
          },
          {
            image: '/static/images/new/main_home_show_one.png',
          },
          {
            image: '/static/images/new/main_home_show_three.png',
          },
          {
            image: '/static/images/new/main_home_show_four.png',
          },
        ],
        featLists: [
          {
            image: '/static/images/new/main_home_zqsbtz.png',
            text: '债权申报通知',
          },
          {
            image: '/static/images/new/main_home_wdaj.png',
            text: '我的案件',
          },
          {
            image: '/static/images/new/main_home_zqsb.png',
            text: '债权申报',
          },
          {
            image: '/static/images/new/main_home_zxhy.png',
            text: '在线会议',
          },
        ],
      }
    },
  }
</script>

<style lang="scss" scoped>
  .home-page {
    height: 100%;
    .home-swiper {
      /deep/ .u-indicator-item-round {
        background-color: rgba(255, 255, 255, 0.8);
      }
      /deep/ .u-indicator-item-round-active {
        background-color: rgb(255, 255, 255);
      }
    }
    .home-feats {
      /deep/ .grid-text {
        font-size: 12px;
      }
    }
    .creditor-container {
      margin-top: 24rpx;
      padding: 18rpx 24rpx 0 24rpx;
      background-color: #fff;
      height: calc(100% - 484rpx);
      .title_bar {
        display: flex;
        justify-content: space-between;
        margin-bottom: 24rpx;
        .name {
          font-weight: bold;
          position: relative;
          z-index: 1;
          &::after {
            position: absolute;
            z-index: -1;
            content: '';
            top: 0;
            left: 0;
            width: 96rpx;
            height: 40rpx;
            border-radius: 0 20rpx 0 0;
            background: linear-gradient(to bottom, #d9ecfd, #f0f7fe);
          }
        }
      }
      .creditor_lists {
        padding: 0 18rpx;
        height: calc(100% - 64rpx);
        overflow: auto;
      }
    }
  }
</style>
