<template>
  <div>
    <h1>Title</h1>
    <div>
      <nuxt-content :document="articles" />
    </div>
  </div>
</template>
<script>
export default {
  async asyncData({ $content, params }) {
    const articles = await $content('articles', params.slug).fetch()

    return { articles }
  },
}
</script>
