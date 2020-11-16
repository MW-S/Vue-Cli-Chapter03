<template>
  <div class="main"  id="login">
    <div class="row" align="center">
       <div class="navbar navbar-default " style="width: 305px;">
         <div class="navbar-header">
           <!-- .navbar-toggle样式用于toggle收缩的内容，即nav-collapse collapse样式所在元素 -->
           <button class="navbar-toggle" type="button" data-toggle="collapse" data-target=".navbar-responsive-collapse">
             <span class="sr-only">Toggle Navigation</span>
             <span class="icon-bar"></span>
             <span class="icon-bar"></span>
             <span class="icon-bar"></span>
           </button>
           <!-- 确保无论是宽屏还是窄屏，navbar-brand都显示 -->
           <a class="navbar-brand">{{title}}</a>
         </div>
         <div class="collapse navbar-collapse navbar-responsive-collapse">
           <ul class="nav navbar-nav">
            <li id="firstTab" @click="choice = 'first'" :class="choice=='first'?'active':''">
                <a href="javascript:;" @click="compontentName = 'CommonLogin',cur=0" :class="{active:cur == 0}">账号登录</a>
             </li>
             <li id="sencondTab" @click="choice = 'second'" :class="choice=='second'?'active':''">
                <a href="javascript:;" @click="compontentName = 'QRCodeLogin',cur=1" :class="{active:cur == 1}">二维码登录</a>
              </li>
           </ul>
         </div>
       </div>
       <transition enter-active-class="animated bounceInDown"
                    :duration="{ enter: 1000}">
          <component :is="compontentName"></component>
       </transition>
    </div>
  </div>
</template>

<script>
import CommonLogin from '@/components/CommonLogin.vue'
import QRCodeLogin from '@/components/QRCodeLogin.vue'

export default {
  map: 'login',
  components: {
    CommonLogin: CommonLogin,
    QRCodeLogin: QRCodeLogin
  },
  data () {
    return {
      compontentName: 'CommonLogin',
      cur: 0,
      choice: 'first',
      title: '登录方式'
    }
  }
}
</script>

<style>
  .main {
    height: 500px;
    box-shadow: 10px 10px 5px #bbb;
    background-color: #f8f8f8;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .main div p {
    font-size: 30px;
  }
</style>
