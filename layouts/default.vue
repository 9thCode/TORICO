<template>
  <div>
    <TheHeader />
    <Nuxt />
    <TheFooter />
  </div>
</template>

<style lang="scss">
#__nuxt{
  padding-top: 100px;
  @include media(sm){
    padding-top: 60px;
  }
}
</style>