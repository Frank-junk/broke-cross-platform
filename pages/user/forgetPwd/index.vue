<template>
  <view class="forgetPwd-page">
    <u-form :model="forgetForm" ref="forgetFormRule">
      <u-form-item
        left-icon="lock-open"
        prop="newPassword"
        class="newPassword-item"
      >
        <u-input
          v-model="forgetForm.newPassword"
          type="password"
          placeholder="8~16位，包含大写、小写字母、数字"
        />
      </u-form-item>
      <u-form-item
        left-icon="lock-open"
        prop="againPassword"
        class="againPassword-item"
      >
        <u-input
          v-model="forgetForm.againPassword"
          type="password"
          placeholder="请再次输入新的登录密码"
        />
      </u-form-item>
      <u-form-item left-icon="account" prop="realName" class="realName-item">
        <u-input v-model="forgetForm.realName" placeholder="请输入真实姓名" />
      </u-form-item>
      <u-form-item left-icon="account" prop="idCard" class="idCard-item">
        <u-input v-model="forgetForm.idCard" placeholder="请输入证件号码" />
      </u-form-item>
    </u-form>
    <u-button :ripple="true" :hair-line="false" class="forgetPwd-submit">
      提交
    </u-button>
  </view>
</template>

<script>
  export default {
    data() {
      return {
        forgetForm: {
          newPassword: '',
          againPassword: '',
          realName: '',
          idCard: '',
        },
        forgetFormRules: {
          newPassword: [
            {
              required: true,
              message: '请输入新密码',
              // 可以单个或者同时写两个触发验证方式
              trigger: ['change', 'blur'],
            },
          ],
          againPassword: [
            {
              required: true,
              message: '请输入新密码',
              // 可以单个或者同时写两个触发验证方式
              trigger: ['change', 'blur'],
            },
          ],
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
      this.$refs.forgetFormRule.setRules(this.forgetFormRules)
    },
  }
</script>

<style lang="scss" scoped>
  .forgetPwd-page {
    padding: 24px 24px 0 24px;
    /deep/ .u-form-item {
      border: 1px solid #e4e7ed;
      padding: 10px 16px;
      &:nth-child(1) {
        // border-bottom: none;
      }
      &:nth-child(2) {
        border-top: none;
      }
      &:nth-child(3) {
        margin-top: 24px;
      }
      &:nth-child(4) {
        border-top: none;
      }
    }
    // 这里的样式是为了兼容微信小程序
    /deep/ .againPassword-item .u-form-item {
      border-top: none;
    }
    /deep/ .idCard-item .u-form-item {
      border-top: none;
    }
    /deep/ .realName-item .u-form-item {
      margin-top: 24px;
    }
    .forgetPwd-submit {
      margin-top: 24px;
      background-color: #0079fe;
      color: #fff;
      border-radius: 8rpx;
      /deep/ button {
        background-color: transparent;
        color: #fff;
        border-color: transparent;
      }
    }
  }
</style>
