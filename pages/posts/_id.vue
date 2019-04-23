<template>
  <div class="container">
    <article>
      <h1 class="title">{{post.title}}</h1>
      <p>{{post.content}}</p>
    </article>
    <aside>
      <h3>Posts you might enjoy</h3>
      <ul>
        <li v-for='related in relatedPosts'>
          <nuxt-link :to="`/posts/${related.id}`">{{related.title}}</nuxt-link>
        </li>
      </ul>
    </aside>
  </div>
</template>

<script>
export default {

  name: 'post',

  data () {
    return {
      id: this.$route.params.id,
      posts: [
        {
          id: '1',
          title: 'Post 1',
          content: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Veritatis iusto inventore consequatur, ullam! Tenetur deleniti blanditiis, eveniet ratione veniam quisquam alias molestias laborum tempore nemo quia explicabo velit error recusandae!'
        },
        {
          id: '2',
          title: 'Post 2',
          content: 'Far far away, behind the word mountains, far from the countries Vokalia and Consonantia, there live the blind texts. Separated they live in Bookmarksgrove right at the coast of the Semantics, a large language ocean. A small river named Duden flows by their place and supplies it with the necessary regelialia. It is a paradisematic country, in which roasted parts of sentences fly into your mouth. '
        },
        {
          id: '3',
          title: 'Post 3',
          content: 'One morning, when Gregor Samsa woke from troubled dreams, he found himself transformed in his bed into a horrible vermin. He lay on his armour-like back, and if he lifted his head a little he could see his brown belly, slightly domed and divided by arches into stiff sections. The bedding was hardly able to cover it and seemed ready to slide off any moment. His many legs, pitifully thin compared with the size of the rest of him, waved about helplessly as he looked. '
        }
      ]
    }
  },
  computed: {
    post () {
      return this.posts.find(post => post.id === this.id)
    },
    relatedPosts () {
      return this.posts.filter(post => post.id !== this.id)
    }
  }
}
</script>

<style lang="css" scoped>
  .container {
    display: flex;
    justify-content: space-between;
    line-height: 1.5;
  }
  article * {
    margin-bottom: 1rem;
  }
  aside {
    min-width: 280px;
    max-width: 280px;
    padding-left: 2rem;
  }
  .title {
    font-size: 2rem;
  }
</style>
