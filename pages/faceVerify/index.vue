<template>
  <view class="face-page">
    <image class="face-img" src="/static/images/face_verify.png"></image>
    <u-form :model="faceForm" ref="faceFormRule" class="face-form">
      <u-form-item left-icon="account" prop="realName" class="realName-item">
        <u-input v-model="faceForm.realName" placeholder="请输入真实姓名" />
      </u-form-item>
      <u-form-item left-icon="account" prop="idCard" class="idCard-item">
        <u-input v-model="faceForm.idCard" placeholder="请输入证件号码" />
      </u-form-item>
    </u-form>
    <u-button :ripple="true" :hair-line="false" class="face-submit">
      实名认证
    </u-button>
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
        },
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
    .face-form {
      padding: 0 24px;
      /deep/ .u-form {
        padding: 0 24px;
      }
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
    .face-submit {
      margin-top: 24px;
      background-color: #0079fe;
      color: #fff;
      border-radius: 8rpx;
      width: calc(100% - 48px);
      /deep/ button {
        background-color: transparent;
        color: #fff;
        border-color: transparent;
      }
    }
  }
</style>
