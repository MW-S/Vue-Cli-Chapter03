<template>
  <div class="container" style="width: 500px;">
    <div class="alert alert-danger alert-dismissable" v-if="error" role="alert">
      {{errorMsg}}
    </div>
    <div class="alert alert-success"  v-if="success" role="alert">{{errorMsg}}</div>
    <div class="compareNumber" style="flex-direction: column;">
      <div >
        <label>账号：</label>
        <input class="form-control" style="width: 300px;" type="text" v-model="account" name="text" id="account" placeholder= "请输入账号" />
      </div>
      <div>
        <label >密码：</label>
        <input class="form-control" style="width: 300px;" type="text" v-model="pwd" name="text" id="pwd" placeholder="请输入密码" />
      </div>
    </div>
    <div class="compareNumber"  style="padding: 0px 120px;margin-top: 10px;">
      <a class="btn btn-info btn-lg btn-block" @click="login()">登录</a>
    </div>
    <div class="compareNumber"  style="margin-top: 10px;">
      <label>用于测试的账号与密码：</label>
      <label>账号：admin</label>
      <label>密码：123456</label>
    </div>
  </div>
</template>

<script>

export default {
  name: 'CommonLogin',
  data () {
    return {
      msg: 'loginTemplate',
      account: '',
      pwd: '',
      error: false,
      errorMsg: '',
      success: false
    }
  },
  methods: {
    login () {
      var account = this.account
      var pwd = this.pwd
      if (account === 'admin' && pwd === '123456') {
        this.error = false
        this.success = true
        this.errorMsg = '登录成功！'
      } else if (account === 'admin' && pwd !== '123456') {
        this.success = false
        this.error = true
        this.errorMsg = '密码错误！'
      } else {
        this.success = false
        this.error = true
        this.errorMsg = '用户不存在！'
      }
      return ''
    }
  },
  beforeCreate () {
    console.log(this.$route)
    var co = this.$route.query.choice
    console.log(co)
    this.$root.$data.choice = co
  }
}
</script>

<style>
</style>
