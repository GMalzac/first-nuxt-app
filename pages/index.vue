<template>
  <section class="container">
    <div>
      <logo/>
      <h1 class="title">
        nuxt-fundamentals
      </h1>
      <h2 class="subtitle">
        My gnarly Nuxt.js project
      </h2>
      <div class="links">
        <nuxt-link v-for="post in posts"
          :to="{name: 'posts-id', params: {id: post.id}}"
          :key="post.id"
          class="button--grey"
        >
          {{post.title}}

        </nuxt-link>
        <a
          href="https://nuxtjs.org/"
          target="_blank"
          class="button--green">Documentation</a>
        <a
          href="https://github.com/nuxt/nuxt.js"
          target="_blank"
          class="button--grey">GitHub</a>
      </div>
    </div>
  </section>
</template>

<script>
import Logo from '~/components/Logo.vue'

export default {
  components: {
    Logo
  },
  head () {
    return {
      title: "Home page",
      meta: [
        {name: 'twitter:title', content: "Greg's first Nuxt App"},
        {name: 'twitter:description', content: "This is the very first app!!"},
        {name: 'twitter:image', content: 'https://s3-eu-west-1.amazonaws.com/tpd/logos/526905350000640005771810/0x0.png'},
        {name: 'twitter:card', content: "summary_large_image"}
      ]
    }
  },
  computed: {
    posts () {
      return this.$store.state.posts.all
    }
  }
}
</script>

<style scoped>
.container {
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}
.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
  'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  letter-spacing: 1px;
}
.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
}
.links {
  padding-top: 15px;
}
</style>
