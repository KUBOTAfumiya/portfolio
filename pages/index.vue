<template>
  <Scaffold>
    <div class="hero">
      <div>
        <img src="/images/nightrace.jpg" alt="" />
      </div>
      <canvas ref="canvas" width="2048" height="1367"></canvas>
      <h1 class="title">
        portfolio
      </h1>
    </div>
  </Scaffold>
</template>

<script>
const draw = (ctx, width, height) => {
  const r = 10 // 振幅
  const T = 50 // 周期
  let degree = 0 // 角度
  const k = (2 * Math.PI) / T
  const h = height / 2
  const drawWave = (degree) => {
    ctx.moveTo(0, -r * (Math.sin(k * degree) + h)) // 始点
    for (let x = 1; x <= width; x += 2) {
      const y = -r * Math.sin(k * (degree + x))
      ctx.lineTo(x, y + h)
    }
  }
  const loop = () => {
    // 繰り返される関数

    ctx.lineWidth = 3

    ctx.clearRect(0, 0, width, height)
    ctx.beginPath()
    ctx.strokeStyle = '#0f0'
    drawWave(degree)
    ctx.stroke()

    ctx.beginPath()
    ctx.strokeStyle = '#0f0'
    drawWave(degree + 90)
    ctx.stroke()

    ctx.beginPath()
    ctx.strokeStyle = '#0f0'
    drawWave(degree + 45)
    ctx.stroke()

    degree += 3 // 3度づつ増やしていく

    requestAnimationFrame(loop)
  }

  loop()
}
export default {
  mounted() {
    const ctx = this.$refs.canvas.getContext('2d')

    draw(ctx, this.$refs.canvas.width, this.$refs.canvas.height)
  },
}
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

canvas {
  position: absolute;
  width: 100%;
  height: 100%;
  mix-blend-mode: color-dodge;
}
</style>
