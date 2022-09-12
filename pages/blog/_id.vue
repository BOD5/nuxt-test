<template>
  <div>
    <span>Blog post {{post.id}}</span>
    <h1 class="post-title">{{post.title}}</h1>
    <p class="post-body">{{post.body}}</p>
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
    },
    head: () => {
      return {
        titleTemplate: 'Blog page',
        meta: [
          { charset: 'utf-8' },
          { name: 'viewport', content: 'width=device-width, initial-scale=1' },
  
          // hid is used as unique identifier. Do not use `vmid` for it as it will not work
          { hid: 'description', name: 'description', content: 'Meta description' }
        ]
      }
    }
  }
  </script>

  <style lang="scss" scoped>
  .post-title {
    font-size: 36px;
    font-weight: 700;
    text-transform: capitalize;
  }

  .post-body {
    white-space: pre-line;
  }
  </style>