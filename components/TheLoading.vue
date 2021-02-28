<template lang="pug">
transition(name="fade")
  .loading-page(v-if="loading")
    .loading-logo: img(src="~/assets/images/logo.svg" alt="" width=300)
</template>

<script>
export default {
  data: () => ({
    loading: false
  }),
  methods: {
    start() {
      this.loading = true
    },
    finish() {
      this.loading = false
    }
  },
  mounted() {
    this.$nextTick(() => {
      this.$nuxt.$loading.start()
      setTimeout(() => this.$nuxt.$loading.finish(), 0)
    })
  }
}
</script>

<style lang="scss" scoped>
  .loading-page {
    position: fixed;
    top: 0;
    left: 0;
    z-index: 2000;
    width: 100%;
    height: 100%;
    background: #FFF;
  }

  .loading-logo{
    width: 100%;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;

    img{
      @include media(sm){
        width: 200px;
      }
    }
  }

  .fade-leave-active {
    transition: opacity .5s 1s;
  }

  .fade-leave-to {
    opacity: 0;
  }
</style>