<template>
  <div>
    <span>Blog post {{post.id}}</span>
    <h1 class="post-title">{{post.title}}</h1>
    <p class="post-body">{{post.body}}</p>
  </div>
</template>

<script>
import { /* computed, ref, useFetch, useMeta, useRoute, */ defineComponent } from '@nuxtjs/composition-api'

export default defineComponent({
  // Not working Meta

  // setup() {
  //   const route = useRoute()
  //   const id = computed(() => route.value.params.id)
    
    
  //   const post = ref({});
  //   useFetch(async () => {
  //     const result = await fetch(
  //       `https://jsonplaceholder.typicode.com/posts/${id.value}`
  //     ).then((res) => {
  //       return res.json()
  //     })
  //     if (result) {
  //       post.value = result
  //     } else {
  //       console.log(' - something went wrong:20 >'); // eslint-disable-line no-console
  //     }
  //   })
  //   // useMeta(() => ({meta: [
  //   //   {
  //   //     hid: 'description',
  //   //     name: 'description',
  //   //     content: 'post.value.title'
  //   //   },
  //   // ]}))
  //   useMeta(() => ({ title: post.value.title, }))
  //   return {
  //     post
  //   }
  // },
  // head: {},
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
  head() {
    return {
      titleTemplate: this.post.title,
      meta: [
        { charset: 'utf-8' },
        { name: 'viewport', content: 'width=device-width, initial-scale=1' },

        // hid is used as unique identifier. Do not use `vmid` for it as it will not work
        { hid: 'description', name: 'description', content: 'Meta description' }
      ]
    }
  }
})
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