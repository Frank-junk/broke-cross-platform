<template>
  <view class="face-page">
    <image class="face-img" src="/static/images/face_verify.png"></image>
    <view class="face">
      <u-form :model="faceForm" ref="faceFormRule" class="face-form">
        <u-form-item left-icon="account" prop="realName" class="realName-item">
          <u-input v-model="faceForm.realName" placeholder="请输入真实姓名" />
        </u-form-item>
        <u-form-item left-icon="account" prop="idCard" class="idCard-item">
          <u-input v-model="faceForm.idCard" placeholder="请输入证件号码" />
        </u-form-item>
      </u-form>
      <u-radio-group v-model="faceForm.radio" class="face-type">
        <u-radio
          v-for="(item, index) in radioList"
          :key="index"
          :name="item.name"
          :disabled="item.disabled"
        >
          {{ item.name }}
        </u-radio>
      </u-radio-group>
      <u-button :ripple="true" :hair-line="false" class="face-submit">
        实名认证
      </u-button>
    </view>
  </view>
</template>

<script>
  export default {
    data() {
      return {
        faceForm: {
          newPassword: '',
          againPassword: '',
          realName: '',
          idCard: '',
          radio: '反光识别',
        },

        radioList: [
          {
            name: '反光识别',
            disabled: false,
          },
          {
            name: '读数识别',
            disabled: false,
          },
        ],
        faceFormRules: {
          realName: [
            {
              required: true,
              message: '请输入真实姓名',
              // 可以单个或者同时写两个触发验证方式
              trigger: ['change', 'blur'],
            },
          ],
          idCard: [
            {
              required: true,
              message: '请输入证件号码',
              // 可以单个或者同时写两个触发验证方式
              trigger: ['change', 'blur'],
            },
          ],
        },
      }
    },
    // 必须要在onReady生命周期，因为onLoad生命周期组件可能尚未创建完毕
    onReady() {
      this.$refs.faceFormRule.setRules(this.faceFormRules)
    },
  }
</script>

<style lang="scss" scoped>
  .face-page {
    .face-img {
      width: 100%;
      height: 380rpx;
      margin-bottom: 24px;
    }
    .face {
      padding: 0 24px;
    }
    /deep/ .u-form-item {
      border: 1px solid #e4e7ed;
      padding: 10px 16px;
      &:nth-child(1) {
        // margin-top: 24px;
      }
      &:nth-child(2) {
        border-top: none;
      }
    }
    /deep/ .idCard-item .u-form-item {
      border-top: none;
    }
    .face-type {
      display: inline-block;
      margin-top: 24px;
    }
    .face-submit {
      margin-top: 24px;
      background-color: #0079fe;
      color: #fff;
      border-radius: 8rpx;
      width: 100%;
      /deep/ button {
        background-color: transparent;
        color: #fff;
        border-color: transparent;
      }
    }
  }
</style>
