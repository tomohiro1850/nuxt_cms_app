<template>
  <ul>
    <li v-for="content in contents" :key="content.id">
      <nuxt-link :to="`/${content.id}`">
        {{ content.title }}
      </nuxt-link>
    </li>
  </ul>
</template>

<script>
    import axios from 'axios'
    export default {
        async asyncData() {
        const { data } = await axios.get(
            // your-service-id部分は自分のサービスidに置き換えてください
            'https://sample1850.microcms.io/api/v1/entry',
            {
                // your-api-key部分は自分のapi-keyに置き換えてください
                headers: { 'X-API-KEY': '7800a760-efe5-425e-830b-6dc4efb6a668' }
            }
        )
        return data
    }
    }
</script>