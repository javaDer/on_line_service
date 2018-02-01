<template>
  <mt-tabbar v-model="selected">
    <mt-tab-item id="首页">
      <img slot="icon" src="../assets/images/home.png">
      首页




    </mt-tab-item>
    <mt-tab-item id="发现">
      <img slot="icon" src="../assets/images/find.png">
      发现





    </mt-tab-item>
    <mt-tab-item id="我的">
      <img slot="icon" src="../assets/images/my.png">
      我的




    </mt-tab-item>
  </mt-tabbar>
</template>
<script>
  export default{
    name: "Footer",
    data () {
      return {
        selected: '首页'
      }
    }

  }
</script>
