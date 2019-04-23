<template>
  <div class="container">
    <article>
      <h1 class="title">
        What is lorem ipsum?
      </h1>
      <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Rerum necessitatibus ut commodi, dicta deserunt iste quaerat velit labore! Velit nesciunt tempora aspernatur eligendi voluptates veritatis totam ipsam? Officiis necessitatibus, facilis!</p>
    </article>
  </div>
</template>

<script>
export default {

  name: 'post',

  data () {
    return {

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
