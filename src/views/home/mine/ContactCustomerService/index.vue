<template>
  <div class="register">
    <!-- 顶部导航栏 -->
    <van-nav-bar :title="$t('联系客服')" @click-left="onClickLeft" left-arrow />
    <div class="mine-content">
      <div class="title">{{$t('邮箱地址')}}</div>
      <p>HGF_Mia@yahoo.com</p>
      <button @click="doCopy('HGF_Mia@yahoo.com')" class="btn">{{$t('复制')}}</button>
    </div>
    <div class="mine-content">
      <div class="title">{{$t('邮箱地址')}}</div>
      <p>HGF_daria@yahoo.com</p>
      <button @click="doCopy('HGF_daria@yahoo.com')" class="btn">{{$t('复制')}}</button>
    </div>
  </div>
</template>

<script>
export default {
  // SMS_EVERY_SEND
  data () {
    return {};
  },
  methods: {
    onClickLeft () {
      // this.$router.push({ name: "login" });
      window.history.go(-1);
    },
    doCopy (text) {
      this.$copyText(text).then(
        e => {
          // success
          this.$toast({
            /*这是使用了element-UI的信息弹框*/
            message: this.$t("邮箱地址复制成功！")
          });
        },
        e => {
          // fail
          this.$toast({
            message: this.$t("复制失败，请手动选择复制！")
          });
        }
      );
    }
  }
};
</script>

<style lang="less" scoped>
@import '../../../../style/mixin.less';
.register {
  height: 100%;
  display: flex;
  flex-direction: column;
  overflow: hidden;
  .mine-content {
    width: 6.62rem;
    margin: 0.3rem auto 0;
    text-align: center;
    background: #fff;
    border-radius: 0.1rem;
    padding: 0 0.26rem 0.4rem;
    border: 1px solid #ffc1c9;
    box-sizing: border-box;
    .title {
      line-height: 1rem;
      color: #000;
      font-size: 0.32rem;
      border-bottom: 1px solid #ececec;
    }
    p {
      line-height: 1.44rem;
      color: #101010;
      font-size: 0.3rem;
      word-break: break-all;
      margin: 0 0.3rem;
    }
    button {
      font-size: 0.3rem;
      color: #ef314b;
      font-weight: normal;
      background: #ffc1c9;
      border: 0;
      width: 5.14rem;
      height: 0.86rem;
      line-height: 0.86rem;
      margin-top: 0.2rem;
      border-radius: 0.1rem;
    }
  }
}
</style>