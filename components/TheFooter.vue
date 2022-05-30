<template lang="pug">
footer#footer
  .container.footer-container
    .footer-info
      .footer-logo: nuxt-link(v-scroll-to="'#__nuxt'" to): img(src="~/assets/images/logo.svg" alt="" width="140")
      .footer-content
        address.footer-address 〒689-3221 鳥取県西伯郡大山町富長159-1 BIKAI 2F
        .footer-tel
          dl.footer-tel__dl
            dt TEL
            dd 0859-54-3785<br>
          span.footer-tel__caption ご予約やご利用・ワーケーションについては、お問い合わせ<br class="hide-sm hide-md">フォームよりご相談ください。
        .footer-sns
          ul.footer-sns__list
            li: a(href="https://www.facebook.com/torico.daisen" target="_blank"): font-awesome-icon(:icon="['fab', 'facebook']")
            li: a(href="https://www.instagram.com/torico.daisen/" target="_blank"): font-awesome-icon(:icon="['fab', 'instagram']")
    .footer-company
      dl.footer-company__list
        dt 運営会社：
        dd: a(href="http://amalate.co.jp/business/daisen.html" target="_blank") 株式会社アマゾンラテルナ鳥取大山オフィス
  .copyright
    p: small ©TORICO
</template>

<style lang="scss" scoped>
#footer{
  background-color: #f3f3f3;
  padding-top: 20px;
  @include media(md-lg){
    padding-top: 60px;
  }
}

.footer-info{
  display: flex;
  justify-content: center;
  @include media(sm){
    flex-direction: column;
  }
}

.footer-logo{
  padding-left: 20px;
  padding-right: 20px;
  @include media(sm){
    text-align: center;
    padding-top: 20px;
    padding-bottom: 20px;
  }
}

.footer-content{
  padding-left: 20px;
  padding-right: 20px;
  @include media(sm){
    text-align: center;
  }
}

.footer-sns{
  &__list{
    display: flex;
    justify-content: center;
    font-size: 40px;
    
    a{
      color: inherit;
    }
    li{
      padding-left: 10px;
      padding-right: 10px;
    }
  }
}

.footer-tel{
  margin-top: -5px;
  &__dl{
    font-size: 41px;
    font-weight: 700;
    margin-bottom: -5px;
    @include media(sm){
      font-size: 26px;
      text-align: center;
      margin-top: 0.5em;
    }
    dt{
      display: inline-block;
    }
    dd{
      display: inline-block;
      margin-left: 0.3em;
    }
  }

  &__caption{
    display: block;
    font-size: 0.87em;
    line-height: 1.5;
    @include media(sm){
      margin-top: 5px;
    }
  }
}

.footer-company{
  padding-top: 15px;
  @include media(sm){
    margin-bottom: 20px;
  }
  @include media(md-lg){
    padding-top: 60px;
  }
  &__list{
    text-align: center;
    dt, dd{
      display: inline-block;
    }
  }
}

.copyright{
  text-align: center;
  background-color: #000;
  color: #FFF;
  padding-top: 15px;
  padding-bottom: 15px;
  @include media(md-lg){
    margin-top: 60px;
  }
  p{
    margin-bottom: 0;
  }
}
</style>