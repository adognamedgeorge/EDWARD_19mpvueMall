<template>
  <div class="outerWrap">
    <div class="homeHead">
      <ul>
        <li>酒水饮料</li>
        <li>生鲜水果</li>
        <li>地方特产</li>
        <li>成人情趣</li>
        <li>酒水饮料</li>
        <li>生鲜水果</li>
        <li>地方特产</li>
        <li>成人情趣</li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: 'homeHead'
}
</script>

<style scoped lang="scss">
.homeHead {
  overflow-y: hidden;
  overflow-x: scroll;
  background-color: lightgrey;
  ul {
    margin: 0;
    padding: 0;
    height: rpx(90);
    line-height: rpx(60);
    white-space: nowrap;
    li {
      font-size: .3rem;
      padding: 0 rpx(20);
      display: inline-block;
    }
  }
}
.outerWrap {
  height: rpx(60);
  overflow: hidden;
}
</style>
