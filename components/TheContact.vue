<template lang="pug">
div
  ValidationObserver(ref="obs" v-slot="ObserverProps")
    dl.contact-dl
      dt お問い合わせ内容
      dd
        validation-provider(name="お問い合わせ内容" v-slot="{ errors }" rules="required")
          select.input-select.input-full(name="お問い合わせ内容" v-model="formData.yourTitle")
            option(value="料金プランについて") 料金プランについて
            option(value="ワーケーションについて") ワーケーションについて
            option(value="イベント利用について") イベント利用について
            option(value="その他") その他
          .panel__error {{ errors[0] }}
    dl.contact-dl
      dt お名前
        span.color-required *
      dd
        validation-provider(name="お名前" v-slot="{ errors }" rules="required")
          input(name="お名前" type="text" v-model="formData.yourName").input-text.input-full
          .panel__error {{ errors[0] }}
    dl.contact-dl
      dt ふりがな
        span.color-required *
      dd
        validation-provider(name="ふりがな" v-slot="{ errors }" rules="required")
          input(name="ふりがな" type="text" v-model="formData.yourFurigana").input-text.input-full
          .panel__error {{ errors[0] }}
    dl.contact-dl
      dt 会社名 / ご所属
      dd
        input(name="会社名 / ご所属" type="text" v-model="formData.yourCompany").input-text.input-full
    dl.contact-dl
      dt メールアドレス
        span.color-required *
      dd
        validation-provider(name="メールアドレス" v-slot="{ errors }" rules="required|email")
          input(type="email" v-model="formData.yourEmail").input-text.input-full
          .panel__error {{ errors[0] }}
    dl.contact-dl
      dt 電話番号
        span.color-required *
      dd
        validation-provider(name="電話番号" v-slot="{ errors }" rules="required")
          input(name="電話番号" type="tel" v-model="formData.yourTel").input-text.input-full
          .panel__error {{ errors[0] }}
    dl.contact-dl
      dt お問い合わせ内容
        span.color-required *
      dd
        validation-provider(name="お問い合わせ内容" v-slot="{ errors }" rules="required")
          textarea(name="お問い合わせ内容" rows="7" v-model="formData.yourContent").input-full
          .panel__error {{ errors[0] }}
    .form-acceptance
      label.label-checkbox(:class="(formData.acceptance === true) ? 'checked' : ''")
        input(name="プライバシーポリシーの同意" type="checkbox" v-model="formData.acceptance")
      span
        a(href="/privacy.pdf" target="_blank") 当社のプライバシーポリシー
        |に同意して送信する
    //- pre {{ $data }}
    .form-footer
      button.button.button-primary.button-rounded(type='button' v-on:click="submit" :disabled="ObserverProps.invalid || !ObserverProps.validated || formData.acceptance == false") 送信する
</template>

<script>
export default {
  props: {
    formid: {
      type: String,
      required: true
    }
  },
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
  methods: {
    submit(){

      const formData  = this.convertJsontoUrlencoded(this.formData)
      const USER      = process.env.WPUSER
      const PASSWORD  = process.env.APPLICATION_PASSWORD
      const POSTURL   = `${process.env.WP_REST_API_BASE_URL}wp-json/contact-form-7/v1/contact-forms/${this.formid}/feedback/`
      const THNAKSURL = `/form/thanks/`

      // Base64に変換
      const TOKEN = window.btoa(`${USER}:${PASSWORD}`)
      const axiosConfig = {
        headers: {
          'Authorization': `Basic ${TOKEN}`,
          'Content-Type': 'application/x-www-form-urlencoded; charset=utf-8'
        }
      }

    this.submitBlind = true
    this.$axios
      .post(POSTURL, formData, axiosConfig)
      .then(response => {
        console.log(response)
        this.responseData = response.data
        this.submitBlind = true
        this.$router.push(THNAKSURL)
      })
      .catch(error => {
        console.log(error)
        this.submitBlind = false
      })
    },

    convertJsontoUrlencoded(obj) {
      let str = [];
      for (let key in obj) {
        if (obj.hasOwnProperty(key)) {
          str.push(encodeURIComponent(key) + "=" + encodeURIComponent(obj[key]))
        }
      }
      return str.join("&");
    }
  }
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

.panel__error{
  color: red;
  text-align: right;
  padding-top: 5px;
  padding-bottom: 5px;
}

button:disabled{
  background-color: #CCC;
  border-color: #CCC;
  &:hover{
    background-color: #CCC;
    border-color: #CCC;
    color: #FFF;
  }
}
</style>