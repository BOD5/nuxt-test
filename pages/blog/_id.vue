<template>
  <div>
    <h1>{{post.title}}</h1>
    <p>{{post.body}}</p>
  </div>
</template>

<script>
  export default {
    async asyncData({ params }) {
      const post = await fetch(
        `https://jsonplaceholder.typicode.com/posts/${params.id}`
      ).then((res) => res.json())
  
      if (post) {
        return {
          post
        }
      } else {
        console.log(' - something went wrong:20 >'); // eslint-disable-line no-console
      }
    }
  }
  </script>