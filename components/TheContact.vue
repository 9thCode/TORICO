<template lang="pug">
div
  dl.contact-dl
    dt お問い合わせ内容
    dd
      select.input-select.input-full( v-model="formData.yourTitle")
        option(value="料金プランについて") 料金プランについて
        option(value="ワーケーションについて") ワーケーションについて
        option(value="イベント利用について") イベント利用について
        option(value="その他") その他
  dl.contact-dl
    dt お名前
      span.color-required *
    dd
      input(type="text" v-model="formData.yourName").input-text.input-full
  dl.contact-dl
    dt ふりがな
      span.color-required *
    dd
      input(type="text" v-model="formData.yourFurigana").input-text.input-full
  dl.contact-dl
    dt 会社名 / ご所属
    dd
      input(type="text" v-model="formData.yourCompany").input-text.input-full
  dl.contact-dl
    dt メールアドレス
      span.color-required *
    dd
      input(type="email" v-model="formData.yourEmail").input-text.input-full
  dl.contact-dl
    dt 電話番号
      span.color-required *
    dd
      input(type="tel" v-model="formData.yourTel").input-text.input-full
  dl.contact-dl
    dt お問い合わせ内容
      span.color-required *
    dd
      textarea(rows="7" v-model="formData.yourContent").input-full
  .form-acceptance
    label.label-checkbox(:class="(formData.acceptance === true) ? 'checked' : ''")
      input(type="checkbox" v-model="formData.acceptance")
    span
      a(href="/privacy.pdf" target="_blank") 当社のプライバシーポリシー
      |に同意して送信する
  .form-footer
    //- |{{formData}}
    button.button.button-primary.button-rounded(type='submit') 送信する
</template>

<script>
export default {
  data(){
    return {
      formData: {
        yourTitle: '',
        yourName: '',
        yourFurigana: '',
        yourCompany: '',
        yourEmail: '',
        yourTel: '',
        yourContent: '',
        acceptance: false
      }
    }
  },
}
</script>

<style lang="scss" scoped>
.contact-dl{
  margin-bottom: 1em;
  dt{
    margin-bottom: 0.5em;
    padding-left: 10px;
  }
  dd{

  }

}

.form-acceptance{
  text-align: center;
  @include media(sm){
    text-align: left;
    display: flex;
    align-items: flex-start;
    position: relative;
  }

  label{
    @include media(sm){
      margin-left: -10px;
      margin-top: -10px;
    }
  }

  span{
    @include media(sm){
      padding-left: 10px;
    }
  }
}

.form-footer{
  text-align: center;
  margin-top: 2em;
}
</style>