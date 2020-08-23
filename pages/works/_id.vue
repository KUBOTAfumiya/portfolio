<template>
  <Scaffold>
    <div>
      <h2>{{ item.title }}</h2>
    </div>
  </Scaffold>
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
