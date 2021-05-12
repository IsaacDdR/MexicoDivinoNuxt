<template>
  <section class="text-gray-600 body-font bg-vinos">
    <div
      class="container mx-auto flex flex-col px-5 py-24 justify-center items-center"
    >
      <img
        class="lg:w-2/6 md:w-3/6 w-5/6 mb-10 object-cover object-center rounded"
        alt="hero"
        src="~/assets/img/logo-md.png"
      />
      <div class="w-full md:w-2/3 flex flex-col mb-16 items-center text-center">
        <h1
          class="title-font sm:text-4xl text-3xl mb-4 font-medium text-gray-900"
        >
          Knausgaard typewriter readymade marfa
        </h1>
        <p class="mb-8 leading-relaxed">
          <nuxt-content :document="articles" />
        </p>
      </div>
    </div>
  </section>
</template>
<script>
export default {
  async asyncData({ $content }) {
    const articles = await $content().fetch()
    return {
      articles,
    }
  },
}
</script>
