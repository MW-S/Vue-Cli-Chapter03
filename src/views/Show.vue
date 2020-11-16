<template>
  <div class="main"  id="boxShow">
    <boxShow></boxShow>
  </div>
</template>

<script>
import boxShow from '@/components/BoxShow.vue'

export default {
  map: 'boxShow',
  components: {
    boxShow
  }
}
</script>

<style lang="css">
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
