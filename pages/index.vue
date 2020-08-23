<template>
  <div class="hero">
    <div>
      <img src="/images/nightrace.jpg" alt="" />
    </div>
    <h1 class="title">
      portfolio
    </h1>
  </div>
</template>

<script>
export default {}
</script>

<style lang="scss" scoped>
.hero {
  position: relative;

  img {
    vertical-align: middle;
  }

  .title {
    position: absolute;
    color: #fff;
    mix-blend-mode: exclusion;
    bottom: 20px;
    right: 20px;
    font-size: 60px;
  }
}
</style>
