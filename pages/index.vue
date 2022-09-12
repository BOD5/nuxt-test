<template>
  <ul>
    <li v-for="post of posts" :key="post.id"><nuxt-link :to="`/blog/${post.id}`" class="link">{{post.title}}</nuxt-link></li>
  </ul>
</template>

<script>
export default {
  name: 'IndexPage',
  async asyncData({ params, redirect }) {
    const posts = await fetch(
      'https://jsonplaceholder.typicode.com/posts/'
    ).then((res) => res.json())

    if (posts) {
      return {
        posts
      }
    } else {
      redirect('/')
    }
  }
}
</script>
