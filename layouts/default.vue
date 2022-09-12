<!-- eslint-disable vue/multi-word-component-names -->
<template>
  <div>
    <div class="header">
      <div class="flex justify-between items-center container font-sans text-black m-auto ">
        <h1><nuxt-link to="/" class="link header-link">Blog</nuxt-link></h1>
        <div class="flex">
          <div class="mr-1"><nuxt-link to="/about" class="link header-link">About</nuxt-link></div>
          <div><nuxt-link to="/team" class="link header-link">Team</nuxt-link></div>
        </div>
      </div>
    </div>
    <div class="container font-sans text-black m-auto">
      <Nuxt />
    </div>
  </div>
</template>

<script>
export default {

}
</script>

<style lang="scss">
.header {
  padding: 15px;
}
.header-link {
  font-size: 36px;
}
</style>