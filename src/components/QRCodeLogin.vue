<template>
 <div class="pic">
   <img src="../images/code.jpg">
</div>
</template>

<script>
export default {
  name: 'QRCodeLogin',
  beforeCreate () {
    console.log(this.$route)
    var co = this.$route.query.choice
    console.log(co)
    this.$root.$data.choice = co
  }
}
</script>

<style>
  .pic{
    width: 200px;
    height: 200px;
    margin: 0 auto;
  }
  .pic img{
    width: 100%;
    height: 100%;
  }
</style>
