/* eslint-disable vue/no-v-html */
<template>
  <div>
    <h1 class="title">{{ item.title }}</h1>
    <div class="content">
      <p>
        <a :href="item.url" target="_blank">{{ item.url }}</a>
      </p>
      <div class="tags are-small">
        <span v-for="tool in item.tools" :key="tool" class="tag">{{
          tool
        }}</span>
      </div>
      <figure class="image">
        <img :src="item.thumbnail.url" alt="" />
        <p class="has-text-right is-size-7">画像は開発中のものです</p>
      </figure>
      <div v-html="item.text"></div>
    </div>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  async asyncData({ params }) {
    const { data } = await axios.get(
      `https://portfolio_238.microcms.io/api/v1/work/${params.id}`,
      {
        headers: { 'X-API-KEY': process.env.API_KEY },
      }
    )
    return {
      item: data,
    }
  },
  data() {
    return {
      item: {},
    }
  },
}
</script>
