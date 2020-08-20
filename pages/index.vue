<template>
  <Scaffold>
    <div class="hero">
      <div>
        <img src="/images/nightrace.jpg" alt="" />
      </div>
      <h1 class="title">
        portfolio
      </h1>
    </div>
  </Scaffold>
</template>

<script>
export default {}
</script>

<style lang="scss" scoped>
.hero {
  position: relative;

  .title {
    position: absolute;
    mix-blend-mode: color-dodge;
    color: #fff;
    mix-blend-mode: exclusion;
    bottom: 0;
    font-size: 60px;
  }
}
</style>
