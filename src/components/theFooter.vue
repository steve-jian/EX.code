<template>
  <footer>
    <div class="left">
      <h4>©Yunnet 21st</h4>
    </div>
    <div class="right">
      <h4>{{ now }}</h4>
    </div>
  </footer>
</template>

<script>
export default {
  data() {
    return {
      now: new Date(Date.now()).toLocaleString("zh-TW")
    };
  }
};
</script>

<style scoped>
footer {
  position: fixed;
  bottom: 0px;
  width: 100%;
}
.left {
  float: left;
  width: 50%;
}
.right {
  float: right;
  width: 50%;
}
</style>
