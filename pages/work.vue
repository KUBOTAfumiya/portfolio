<template>
  <Scaffold>
    <h1 class="title">
      Work
    </h1>
    <div class="columns is-multiline">
      <div class="column is-4">
        <div class="card">
          <div class="card-image">
            <figure class="image is-4by3">
              <img
                src="https://bulma.io/images/placeholders/1280x960.png"
                alt="Placeholder image"
              />
            </figure>
          </div>
          <div class="card-content">
            <div class="content">
              Lorem ipsum dolor sit amet, consectetur adipiscing elit. Phasellus
              nec iaculis mauris. <a>@bulmaio</a>.
            </div>
          </div>
        </div>
      </div>
      <div class="column is-4">
        <div class="card">
          <div class="card-content">
            <div class="content">
              Coming Soon
            </div>
          </div>
        </div>
      </div>
    </div>
  </Scaffold>
</template>

<script>
export default {}
</script>

<style lang="scss" scoped>
.column {
  .card {
    height: 100%;
  }
}
</style>
