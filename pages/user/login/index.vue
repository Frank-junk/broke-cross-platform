<template>
  <view class="login-page">
    <view class="login-info">
      <image class="login-logo" src="/static/logo.png"></image>
      <view class="login-name">破产平台</view>
    </view>
    <view class="login-form">
      <u-form :model="loginForm" ref="loginFormRule">
        <u-form-item left-icon="account" prop="account">
          <u-input v-model="loginForm.account" placeholder="请输入登录账号" />
        </u-form-item>
        <u-form-item left-icon="lock-open" prop="password">
          <u-input
            v-model="loginForm.password"
            type="password"
            placeholder="请输入登录密码"
          />
        </u-form-item>
      </u-form>
      <u-button
        :ripple="true"
        :hair-line="false"
        class="login-form_btn"
        @click="handleLogin"
      >
        登录
      </u-button>
      <view class="login-form_other">
        <text>注册新用户</text>
        <text @click="handleRetrievePassword">找回密码</text>
      </view>
    </view>
    <view class="login-desc">--专业高效的破产管理平台--</view>
  </view>
</template>

<script>
  export default {
    data() {
      return {
        loginForm: {
          account: '',
          password: '',
        },
        loginFormRules: {
          account: [
            {
              required: true,
              message: '请输入登录账号',
              // 可以单个或者同时写两个触发验证方式
              trigger: ['change', 'blur'],
            },
          ],
          password: [
            {
              required: true,
              message: '请输入登录密码',
              // 可以单个或者同时写两个触发验证方式
              trigger: ['change', 'blur'],
            },
          ],
        },
      }
    },
    // 必须要在onReady生命周期，因为onLoad生命周期组件可能尚未创建完毕
    onReady() {
      this.$refs.loginFormRule.setRules(this.loginFormRules)
    },
    methods: {
      handleRetrievePassword() {
        this.$Router.push({
          name: 'forgetPwd',
        })
      },
      handleLogin(e) {
        console.log(e)
      },
    },
  }
</script>

<style lang="scss" scoped>
  /deep/ .uni-input-input,
  /deep/ .u-input__input {
    caret-color: #cad1ff;
    color: #cad1ff;
  }
  .login-page {
    color: #fff;
    height: 100%;
    width: 100%;
    background-image: url('@/static/images/user/login_bg.png');
    background-repeat: no-repeat;
    background-size: cover;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: space-between;

    /deep/ .u-form-item__message {
      padding-left: 0 !important;
    }

    /deep/ .uicon-account,
    /deep/ .uicon-lock-open {
      color: #cad1ff;
    }

    .login-info {
      margin-top: 84rpx;
    }

    .login-logo {
      width: 66px;
      height: 74px;
    }

    .login-form {
      width: 70%;
      flex-grow: 2;
      margin-top: 86px;
    }

    .login-form_btn {
      width: 100%;
      color: #0b6bf3;
      margin-top: 36rpx;
      margin-bottom: 12rpx;
    }

    .login-form_other {
      font-size: 24rpx;
      color: #fff;
      display: flex;
      justify-content: space-between;
      height: fit-content;
    }

    .login-desc {
      padding: 56rpx 0;
    }
  }
</style>
