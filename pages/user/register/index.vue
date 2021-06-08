<template>
  <view class="register-page">
    <u-form :model="form" ref="uForm" class="register-form" label-width="100px">
      <u-form-item label="登录账号">
        <u-input v-model="form.name" placeholder="请输入登录账号" />
      </u-form-item>
      <u-form-item label="手机号码">
        <u-input v-model="form.intro" placeholder="请输入登录账号" />
      </u-form-item>
      <u-form-item label="登录密码">
        <u-input v-model="form.sex" placeholder="请输入登录账号" />
      </u-form-item>
      <u-form-item label="确认密码">
        <u-input v-model="form.sex" placeholder="请输入登录账号" />
      </u-form-item>
      <u-form-item label="真实姓名" class="realName-item">
        <u-input v-model="form.sex" placeholder="请输入登录账号" />
      </u-form-item>
      <u-form-item label="身份证号">
        <u-input v-model="form.sex" placeholder="请输入登录账号" />
      </u-form-item>
      <u-form-item label="身份证正反面">
        <u-upload
          :action="action"
          :file-list="fileList"
          :max-count="2"
          :upload-text="uploadText"
        ></u-upload>
      </u-form-item>
      <u-form-item label="邮箱">
        <u-input v-model="form.sex" placeholder="请输入登录账号" />
      </u-form-item>
    </u-form>

    <view class="register-opera">
      <u-button :ripple="true" :hair-line="false" class="register-opera_btn">
        登录
      </u-button>
      <view class="register-opera_tip">已有账户，立即登陆</view>
    </view>
  </view>
</template>

<script>
  export default {
    data() {
      return {
        form: {
          name: '',
          intro: '',
          sex: '',
        },
        checkboxList: [
          {
            name: '苹果',
            checked: false,
            disabled: false,
          },
          {
            name: '雪梨',
            checked: false,
            disabled: false,
          },
          {
            name: '柠檬',
            checked: false,
            disabled: false,
          },
        ],
        radioList: [
          {
            name: '鲜甜',
            disabled: false,
          },
          {
            name: '麻辣',
            disabled: false,
          },
        ],
        radio: '',
        switchVal: false,
        uploadText: '身份证正面',
        action: 'http://www.example.com/upload',
        fileList: [
          {
            url: 'http://pics.sc.chinaz.com/files/pic/pic9/201912/hpic1886.jpg',
          },
          {
            url: 'http://pics.sc.chinaz.com/files/pic/pic9/201912/hpic1886.jpg',
          },
        ],
      }
    },
  }
</script>

<style lang="scss" scoped>
  .register-page {
    .register-form {
      // 这种写法主要是兼容微信小程序
      /deep/ .realName-item {
        margin-top: 24px;
        border-top: 1px solid #efefef;
        .u-form-item {
          margin-top: 24px;
          border-top: 1px solid #efefef;
        }
      }
      /deep/ .u-form-item {
        padding: 20rpx 12px;
      }
    }
    .register-opera {
      padding: 36rpx 12rpx;
      text-align: center;
      .register-opera_btn {
        width: 88%;
        color: #fff;
        background-color: #0b6bf3;
        /deep/ .u-btn {
          color: #fff;
          background-color: #0b6bf3;
          border-radius: 4px;
        }
      }
      .register-opera_tip {
        margin-top: 16rpx;
        color: #0b6bf3;
      }
    }
  }
</style>
