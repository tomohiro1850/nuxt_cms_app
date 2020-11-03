<template>
    <main class="main">
        <h1 class="title">{{ title }}</h1>
        <p class="publishedAt">{{ publishedAt }}</p>
        <div class="post" v-html="body"></div>
    </main>
</template>

<script>
    import axios from 'axios'

    export default {
        async asyncData({ params }) {
        const { data } = await axios.get(
            `https://sample1850.microcms.io/api/v1/entry/${params.slug}`,
            {
                headers: { 'X-API-KEY': '7800a760-efe5-425e-830b-6dc4efb6a668' }
            }
        )
        return data
    }
    }
</script>