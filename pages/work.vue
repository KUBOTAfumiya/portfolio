<template>
  <div>
    <h1 class="title">
      Work
    </h1>
    <div class="columns is-multiline">
      <div v-for="item in items" :key="item.id" class="column is-4">
        <nuxt-link :to="`/works/${item.id}`">
          <div class="card">
            <div class="card-image">
              <figure class="image is-4by3 has-background-light	">
                <img :src="item.thumbnail.url" alt="" />
              </figure>
            </div>
            <div class="card-content">
              <div class="content">
                <p>{{ item.title }}</p>
                <div class="tags are-small">
                  <span v-for="tool in item.tools" :key="tool" class="tag">{{
                    tool
                  }}</span>
                </div>
              </div>
            </div>
          </div>
        </nuxt-link>
      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  async asyncData() {
    const { data } = await axios.get(
      'https://portfolio_238.microcms.io/api/v1/work?fields=id,thumbnail,title,tools',
      {
        headers: { 'X-API-KEY': process.env.API_KEY },
      }
    )
    return {
      items: data.contents,
    }
  },
  data() {
    return {
      items: [],
    }
  },
}
</script>

<style lang="scss" scoped>
.column {
  .card {
    height: 100%;
  }
}
.image {
  img {
    object-fit: contain;
  }
}
</style>
