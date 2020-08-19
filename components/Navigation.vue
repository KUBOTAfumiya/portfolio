<template>
  <nav class="navbar" role="navigation" aria-label="main navigation">
    <div class="navbar-brand">
      <nuxt-link to="/" class="navbar-item">TWO.THREE.EIGHT</nuxt-link>

      <a
        role="button"
        class="navbar-burger burger"
        aria-label="menu"
        aria-expanded="false"
        data-target="navbarBasicExample"
      >
        <span aria-hidden="true"></span>
        <span aria-hidden="true"></span>
        <span aria-hidden="true"></span>
      </a>
    </div>

    <div id="navbarBasicExample" class="navbar-menu">
      <div class="navbar-start">
        <nuxt-link to="/" class="navbar-item">
          Home
        </nuxt-link>

        <nuxt-link to="/about" class="navbar-item">
          About
        </nuxt-link>

        <nuxt-link to="/work" class="navbar-item">
          Work
        </nuxt-link>

        <nuxt-link to="/career" class="navbar-item">
          Career
        </nuxt-link>
      </div>
    </div>
  </nav>
</template>

<script>
export default {}
</script>
