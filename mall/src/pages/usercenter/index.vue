<template>
  <div id="usercenter">
    <div class="triangle"></div>
    <div class="triangle rotate"></div>
    <button>退出登录</button>
  </div>
</template>

<script>
export default {
  name: 'index'
}
</script>

<style scoped lang="scss">
#usercenter {
  .triangle {
    border-width: rpx(100);
    border-style: solid;
    width: 0;
    height: 0;
    border-color: #cccccc transparent transparent transparent;
    margin: 0 auto rpx(50);
  }
  .rotate {
    /*transform: rotate(45deg);*/
    border-color: red yellow grey blue;
  }
  button {
    margin: 0 rpx(50);
  }
}
</style>
