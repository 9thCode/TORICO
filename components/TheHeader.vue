<template lang="pug">
header#header
  //- |{{ $data }}
  .container.header-container
    .header-logo: nuxt-link(to="/"): img(src="~/assets/images/logo.svg" alt="TORICO" width="140")
    nav.header-nav
      ul.header-nav-list
        li.header-nav-list__item
          nuxt-link(v-scroll-to="'#concept'" to :class="{'is-active': scrollY >= sectionOffsetTop[0] && scrollY < sectionOffsetTop[1]}")
            span.header-nav-text.header-nav-text--ja コンセプト
            span.header-nav-text.header-nav-text--en CONCEPT
        li.header-nav-list__item
          nuxt-link(v-scroll-to="'#price'" to :class="{'is-active': scrollY >= sectionOffsetTop[1] && scrollY < sectionOffsetTop[2]}")
            span.header-nav-text.header-nav-text--ja 料金プラン
            span.header-nav-text.header-nav-text--en PLAN
        li.header-nav-list__item
          nuxt-link(v-scroll-to="'#workspace'" to :class="{'is-active': scrollY >= sectionOffsetTop[2] && scrollY < sectionOffsetTop[3]}")
            span.header-nav-text.header-nav-text--ja ワークスペース
            span.header-nav-text.header-nav-text--en WORK SPACE
        li.header-nav-list__item
          nuxt-link(v-scroll-to="'#access'" to :class="{'is-active': scrollY >= sectionOffsetTop[3] && scrollY < sectionOffsetTop[4]}")
            span.header-nav-text.header-nav-text--ja アクセス
            span.header-nav-text.header-nav-text--en ACCESS
        li.header-nav-list__item
          nuxt-link(v-scroll-to="'#contact'" to :class="{'is-active': scrollY >= sectionOffsetTop[4]}")
            span.header-nav-text.header-nav-text--ja お問い合わせ
            span.header-nav-text.header-nav-text--en CONTACT
    i.icon-nav-toggle(v-on:click="navToggle()" :class="(isActive === true) ? 'is-open' : ''")
      span.icon-menubar
        span.bars.bar-1
        span.bars.bar-2
        span.bars.bar-3
    .nav-mobile(:class="(isActive === true) ? 'is-open' : ''")
      ul.nav-mobile-list
        li.nav-mobile-list__item
          nuxt-link(v-scroll-to="'#concept'" to v-on:click.native="navToggle()")
            span.nav-mobile-text.nav-mobile-text--ja コンセプト
            span.nav-mobile-text.nav-mobile-text--en CONCEPT
        li.nav-mobile-list__item
          nuxt-link(v-scroll-to="'#price'" to v-on:click.native="navToggle()")
            span.nav-mobile-text.nav-mobile-text--ja 料金プラン
            span.nav-mobile-text.nav-mobile-text--en PLAN
        li.nav-mobile-list__item
          nuxt-link(v-scroll-to="'#workspace'" to v-on:click.native="navToggle()")
            span.nav-mobile-text.nav-mobile-text--ja ワークスペース
            span.nav-mobile-text.nav-mobile-text--en WORK SPACE
        li.nav-mobile-list__item
          nuxt-link(v-scroll-to="'#access'" to v-on:click.native="navToggle()")
            span.nav-mobile-text.nav-mobile-text--ja アクセス
            span.nav-mobile-text.nav-mobile-text--en ACCESS
        li.nav-mobile-list__item
          nuxt-link(v-scroll-to="'#contact'" to v-on:click.native="navToggle()").button.button-nav--main
            span.nav-mobile-text.nav-mobile-text--ja お問い合わせ
            span.nav-mobile-text.nav-mobile-text--en CONTACT
      ul.nav-mobile-social
        li: a(href="https://www.facebook.com/torico.daisen" target="_blank"): font-awesome-icon(:icon="['fab', 'facebook']")
        li: a(href="https://www.instagram.com/torico.daisen/" target="_blank"): font-awesome-icon(:icon="['fab', 'instagram']")
</template>

<script>

const targets = [
  'concept',
  'price',
  'workspace',
  'access',
  'contact'
];

export default {
  data(){
    return {
      isActive: false,
      path: this.$route.path,
      scrollY: 0,
      sectionOffsetTop: []
    }
  },
  mounted(){
    window.addEventListener('scroll', this.handleScroll)

    targets.forEach(target => {
      const element = document.getElementById(target)
      const offsetTop = Math.round(window.scrollY + element.getBoundingClientRect().top - 100)
      this.sectionOffsetTop.push(offsetTop);
    })

  },
  methods: {
    navToggle: function() {
      this.isActive = !this.isActive
    },
    navClose: function(){
      return this.isActive = false
    },
    handleScroll() {
      this.scrollY = window.scrollY
      targets.forEach((target, index) => {
        const element = document.getElementById(target)
        const offsetTop = Math.round(window.scrollY + element.getBoundingClientRect().top - 100)
        this.sectionOffsetTop[index] = offsetTop;
      })
    }
  },
  watch: {
    '$route' () {
      this.isActive = false,
      this.path = this.$route.path
    }
  }
}
</script>

<style lang="scss" scoped>
#header{
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  z-index: 1000;
  background-color: #fff;
  @include media(sm){
    height: 60px;
  }
}

.header-container{
  position: relative;
}

.header-logo{
  padding: 20px 40px;
  position: absolute;
  top: 20px;
  left: 0;
  z-index: 10;
  background-color: #fff;
  @include media(sm){
    padding: 20px 20px;
    padding-bottom: 10px;
    top: 0;
  }
  
  img{
    @include media(sm){
      width: 80px;
    }
    @include media(md){
      width: 100px;
    }
  }
}

.header-nav{
  display: flex;
  @include media(sm){
    display: none;
  }
  
  &-list{
    margin-left: auto;
    font-weight: 700;
    display: flex;
    &__item{
      margin-left: 2em;
      margin-right: 2em;
      @include media(md){
        margin-left: 1em;
        margin-right: 1em;
        font-size: 14px;
      }
    }

    a{
      color: inherit;
      text-decoration: none;
      display: flex;
      flex-direction: column;
      justify-content: center;
      height: 100px;
      position: relative;
      &.is-active{
        &:before{
          content: "";
          position: absolute;
          display: block;
          position: absolute;
          width: calc(100% - 1em);
          bottom: 0;
          left: 0.5em;
          height: 8px;
          background-color: #0068b7;
        }
      }
    }
  }

  &-text{
    &--ja{
      display: block;
      text-align: center;
    }
    &--en{
      display: block;
      text-align: center;
      &:before,
      &:after{
        content: "-";
      }
    }
  }
}

.icon-nav-toggle {
  width: 51px;
  height: 51px;
  display: block;
  box-sizing: border-box;
  padding: 6px 8px;
  font-size: 10px;
  text-align: center;
  position: absolute;
  z-index: 1020;
  top: 3px;
  right: 5px;
  color: #000;
  @include media(md-lg){
    display: none;
  }
  .menubar-text{
    font-size: 8px;
    position: relative;
    top: 3px;
  }

  .icon-menubar {
    display: block;
    width: 24px;
    height: 26px;
    margin: auto;
    position: relative;
    top: 7px;
    .bars {
      display: block;
      width: 100%;
      height: 3px;
      background-color: #000;
      position: absolute;
      transition: all 0.3s ease-in 0;
      &.bar-1 {
        top: 3px;
      }
      &.bar-2 {
        top: 50%;
        margin-top: -2px;
      }
      &.bar-3 {
        bottom: 4px;
      }
    }
  }

  &.is-open .bars {
    background-color: #fff;
    &.bar-1 {
      top: 11px;
      transform: rotate(45deg);
    }
    &.bar-2 {
      top: 50%;
      margin-top: -2px;
      opacity: 0;
      transform: translateX(50px);
    }
    &.bar-3 {
      bottom: 12px;
      transform: rotate(-45deg);
    }
  }
}

// nav mobile

.nav-mobile{
  position: fixed;
  left: 0;
  z-index: 1010;
  background-color: #000;
  width: 100%;
  height: 100%;
  padding-top: 50px;
  top: -100%;
  transition: all ease 0.5s;
  @include media(md-lg){
    display: none;
  }

  &.is-open{
    top: 0;
  }

  &-list{
    &__item{
      text-align: center;
      margin-top: 2em;
      margin-bottom: 2em;
    }
  }

  a{
    color: #FFF;
    text-decoration: none;
    display: block;
    padding-top: 5px;
    padding-bottom: 5px;
  }

  .button-nav--main{
    flex-direction: column;
    background-color: #fff;
    color: #000;
    border-radius: 100px;
    height: auto;
    margin-left: auto;
    margin-right: auto;
  }
}

.nav-mobile-text{
  font-size: 18px;
  &--ja{
    display: block;
    text-align: center;
  }
  &--en{
    display: block;
    text-align: center;
    &:before,
    &:after{
      content: "-";
    }
  }
}

.nav-mobile-social{
  font-size: 40px;
  text-align: center;

  li{
    display: inline-block;
    margin-left: 10px;
    margin-right: 10px;
  }
}

</style>