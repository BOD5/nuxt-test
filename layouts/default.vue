<!-- eslint-disable vue/multi-word-component-names -->
<template>
  <div class="container font-sans text-black m-auto">
    <div class="flex justify-between items-center">
      <h1><nuxt-link to="/">Blog</nuxt-link></h1>
      <div class="flex">
        <div class="mr-1"><nuxt-link to="/about">About</nuxt-link></div>
        <div><nuxt-link to="/team">Team</nuxt-link></div>
      </div>
    </div>
    <Nuxt />
  </div>
</template>

<script>
export default {

}
</script>

<style>

</style>