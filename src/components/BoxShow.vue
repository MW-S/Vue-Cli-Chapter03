<template>
  <div>
    <div>
      <span>编程语言：</span>
      <ul>
        <li v-for='(item,index) in showList' v-bind:key="index">{{item}}</li>
      </ul>
    </div>
      <a @click="showAll = !showAll" class="btn btn-default btn-info">{{flag}}</a>
   </div>
</template>

<script>
export default {
  name: 'BoxShow',
  data () {
    return {
      list: [
        'C语言', 'C++', 'Java', 'Python', 'Go', 'PHP'// 进行显示的数据
      ],
      showAll: false// 标记数据是否需要完全显示的属性
    }
  },
  computed: {
    showList: function () {
      if (this.showAll === false) {
        var showList = []
        if (this.list.length > 4) { // 一开始显示前4个数据
          for (var i = 0; i < 4; i++) {
            showList.push(this.list[i])
          }
        } else {
          showList = this.list
        }
        return showList
      } else {
        return this.list
      }
    },
    flag: function () {
      if (this.showAll === false) {
        return '单击展开'
      } else {
        return '单击收起'
      }
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
  .status {
    color: red
  }
  .boxBtn {
    text-decoration: none;
    color: black;
    font-size: 16px;
    background: #f1f1f1;
    padding: 5px 10px;
    margin: 0 10px;
    border-radius: 5px;
  }
</style>
