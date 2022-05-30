<template lang="pug">
  main
    .hero
      img(src="~/assets/images/top.jpg" alt="" decoding="async")
    section.section.anchor#concept
      .bg-white
        .container.container--single
          .about-header
            h2.title.about-title 地域の内と外をつなぐ<br>ローカルゲートウェイ
          .about-content
            p 日本海が一望できるオーシャンビューのカウンター席、グループ向けボックス席、利用者と交流できる共有テーブル、オンライン会議も気にせずできるプライベートルームを完備。また、地域の内と外をつなぐゲートウェイとして、地元経営者との交流の場やローカルな暮らしを体験できる場をコーディネートします。
    section.section.anchor#price
      .bg-secondary
        .section-header
          h2.title.section-title 料金プラン
          span.section-title--en PLAN
        .container
          .plan-row
            .plan-box
              .plan-box__header
                h3.title.plan-title--box DROP IN
                p 当日ご利用されたい方
                span.pill-plain 月〜日 10:00〜20:00
              .plan-box__content
                .plan-content
                  h4.plan-content__title [1DAY利用プラン]
                  dl.plan-content__price
                    dt
                      span.unit-currency ￥
                      |1,100
                    dd / 日
                .plan-content
                  h4.plan-content__title [ワーケーションプラン]
                  dl.plan-content__price
                    dt
                      span.unit-currency ￥
                      |2,200
                    dd / 日
                  ul.plan-content__caption
                    li ①滞在中の地域活動・体験をサポート
                    li ②地元住民との交流をコーディネート
            .plan-box
              .plan-box__header
                h3.title.plan-title--box MONTHLY
                p 月額でご利用されたい方
                span.pill-plain 365日 24時間
              .plan-box__content
                .plan-content
                  h4.plan-content__title [個人会員プラン]
                  dl.plan-content__price
                    dt
                      span.unit-currency ￥
                      |16,500
                    dd / 月
                .plan-content
                  h4.plan-content__title [法人会員プラン]
                  dl.plan-content__price
                    dt
                      span.unit-currency ￥
                      |22,000
                    dd / 月
                  ul.plan-content__caption
                    li ※同じ会社・団体の方なら複数利用可
            .plan-box
              .plan-box__header
                h3.title.plan-title--box CHALLENGE
                p 起業やイベントをお考えの方
                span.pill-plain 月〜日 10:00〜20:00
              .plan-box__content
                .plan-content
                  h4.plan-content__title [起業チャレンジプラン]
                  dl.plan-content__price
                    dt
                      span.unit-currency ￥
                      |11,000
                    dd / 月
                  ul.plan-content__caption
                    li.text-center ※最大6ヶ月（それ以降は通常月額料金）
                .plan-content
                  h4.plan-content__title [イベント貸切プラン]
                  dl.plan-content__price
                    dt
                      span.unit-currency ￥
                      |22,000
                    dd / 6h
                  ul.plan-content__caption
                    li.text-center ※6時間以降は￥2,200 /1h
          .plan-row__footer
            p: small ※料金はすべて税込です。
          .plan-service
            h3.title.service-title ご利用できるサービス
            ul.service-list
              li Wi-Fi
              li 電源
              li プロジェクター
              li スクリーン
              li 複合機
              li 55インチモニター
              li ホワイトボード
              li シュレッダー
              li オンライン会議
              li プライベートルーム
    section.section.anchor#workspace
      .bg-white
        .section-header
          h2.title.section-title ワークスペース
          span.section-title--en WORK SPACE
        .container
          .workspace-gallery
            .workspace-block
              .workspace-block__photo: img(src="~/assets/images/counter.jpg" alt="カウンター席")
              .workspace-block__content
                .workspace__titlearea
                  span.pill-plain.workspace-pill カウンター席
                p ちょっとしたお仕事やゆっくり読書などにもご利用できる、日本海を一望するオーシャンビューのカウンター席です。
            .workspace-block
              .workspace-block__photo: img(src="~/assets/images/box.jpg" alt="ボックス席")
              .workspace-block__content
                .workspace__titlearea
                  span.pill-plain.workspace-pill ボックス席
                p 集中してお仕事したい時やグループミーティング・商談などにもご利用できるボックス席です。
            .workspace-block
              .workspace-block__photo: img(src="~/assets/images/booth.jpg" alt="ブース席")
              .workspace-block__content
                .workspace__titlearea
                  span.pill-plain.workspace-pill ブース席
                p フロントと両サイドが仕切られているので、周りを気にせず集中してお仕事や勉強ができる1人用の席です。
            .workspace-block
              .workspace-block__photo: img(src="~/assets/images/shared_table.jpg" alt="共有テーブル")
              .workspace-block__content
                .workspace__titlearea
                  span.pill-plain.workspace-pill 共有テーブル
                p 利用者と交流できる共有テーブルです。人数の多い打ち合わせなどにもご利用できます。
            .workspace-block
              .workspace-block__photo: img(src="~/assets/images/private.jpg" alt="プライベートルーム")
              .workspace-block__content
                .workspace__titlearea
                  span.pill-plain.workspace-pill プライベートルーム
                p 完全な個室なので、本格的な商談やオンライン会議など周りを気にせずご利用できるプライベートルームです。
    section#access.anchor.section
      .bg-secondary
        .section-header
          h2.title.section-title アクセス
          span.section-title--en ACCESS
        .container.access-wrap
          .access-panel
            .access-panel__content
              .access-panel__content--in
                h3.title.access-title TORICO CREATIVE SPACE
                .access-address
                  p: strong 〒689-3221<br>鳥取県西伯郡大山町富長159-1 BIKAI 2F
                .access-time
                  p.mb0 [営業時間 平日 10:00〜20:00]<br>
                  p.small 土日祝は原則月額会員のみ<br>※土日祝にイベントやドロップインをご希望の方は、<br>事前にお問い合わせフォームよりご相談ください。
                .access-detail
                  ul
                    li JR名和駅（山陰本線）より徒歩9分
                    li 米子駅より車で22分、電車で25分
                    li 米子空港より車で35分
                .access-footer
                  a(href="https://www.google.com/maps?ll=35.504267,133.486233&z=15&t=m&hl=ja&gl=JP&mapclient=embed&cid=3258040530758892704" target="_blank").button.button-primary.button-rounded Googleマップを開く
            .access-panel__map
              <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d6496.0009196351375!2d133.48363085476973!3d35.50426685871722!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x0%3A0x2d36e299d3b57ca0!2sTORICO!5e0!3m2!1sja!2sjp!4v1613991249115!5m2!1sja!2sjp" width="600" height="450" style="border:0;" allowfullscreen="" loading="lazy"></iframe>
      section#contact.anchor.section
        .bg-white
          .section-header
            h2.title.section-title お問い合わせ
            span.section-title--en CONTACT
          .container.container-contact.contact-wrap
            .contact-intro
              p 施設に関するご質問やご見学についてなど、お気軽にお問い合わせください。<br>運営会社である株式会社アマゾンラテルナ鳥取大山オフィスよりご連絡させていただきます。
            .contact-main
              TheContact(formid="5")
</template>

<script>
import Meta from '~/plugins/meta'
export default {
  mixins: [Meta],
  data () {
    return {
      meta: {
        title: 'TORICO | 海の見えるコワーキングスペース',
        description: '鳥取県大山町にあるコワーキングスペースTORICO（トリコ）。地方と都会をつなぐゲートウェイとして、経営者やクリエイターとの交流やローカルな暮らしを体験できる場所です。',
        type: 'website',
        url: 'https://torico-daisen.com/',
        image: 'https://torico-daisen.com/ogp.jpg',
      },
    }
  },
}
</script>

<style lang="scss" scoped>

// hero

.hero{
  img{
    width: 100%;
    object-fit: cover;
    @include media(lg){
      height: 700px;
    }
    @include media(md){
      height: 420px;
    }
    @include media(sm){
      height: 210px;
    }
  }
}

// sections

.section-header{
  text-align: center;
  margin-bottom: 4em;
  @include media(sm){
    margin-bottom: 2em;
  }
}

.section-title{
  font-size: 40px;
  @include media(sm){
    font-size: 32px;
  }
  &--en{
    font-size: 25px;
    @include media(sm){
      font-size: 20px;
    }
    &:before,
    &:after{
      content: "-";
      margin-left: 0.5em;
      margin-right: 0.5em;
    }
  }
}

// about

.about-header{
  text-align: center;
  margin-bottom: 4em;
  @include media(sm){
    margin-bottom: 2em;
  }
}

.about-title{
  font-size: 60px;
  @include media(sm){
    font-size: 30px;
  }
}

// plan - main

.plan-row{
  margin-bottom: 1em;
  @include media(sm-md){
    width: 100%;
  }
  @include media(lg){
    display: flex;
    margin-left: -10px;
    margin-right: -10px;
  }

  &__footer{
    text-align: right;
    @include media(sm){
      margin-top: -1em;
    }
  }
}

.plan-box{
  width: 100%;
  border-radius: 10px;
  background-color: #fff;
  padding: 10px;
  @include media(sm){
    padding-top: 3em;
  }
  @include media(sm-md){
    margin-bottom: 2em;
  }
  @include media(md-lg){
    padding: 50px 60px;
  }
  @include media(lg){
    margin-left: 10px;
    margin-right: 10px;
  }

  &__header{
    text-align: center;
    margin-bottom: 3em;
  }
}

.plan-title{
  &--box{
    text-align: center;
    font-size: 33px;
    padding-bottom: 20px;
    margin-bottom: 20px;
    position: relative;
    &:before{
      content: "";
      background-color: $color-primary;
      width: 65px;
      height: 3px;
      display: inline-block;
      position: absolute;
      bottom: 0;
      left: 50%;
      margin-left: -27.5px;
    }
  }
}

.pill-plain{
  border: 1px solid #000;
  display: inline-block;
  border-radius: 100px;
  min-width: 250px;
  padding: 6px 10px;
}

.plan-content{
  margin-bottom: 3em;
  min-height: 8em;
  
  &__title{
    font-weight: 700;
    text-align: center;
    font-size: 20px;
    margin-bottom: 0px;
  }

  &__price{
    text-align: center;
    font-weight: 600;
    dt{
      font-size: 45px;
      display: inline-block;
    }
    dd{
      font-size: 25px;
      display: inline-block;
      margin-left: 0.5em;
    }
  }

  &__caption{
    font-size: 14px;
    text-align: center;
  }
}

.unit-currency{
  display: inline-block;
  // margin-right: 0.3em;
}

// plan - service

.service-title{
  font-size: 25px;
  border-left: 5px solid $color-primary;
  padding-left: 10px;
  padding-top: 5px;
  padding-bottom: 5px;
  margin-bottom: 2em;
  @include media(sm){
    margin-bottom: 1em;
  }
}

.service-list{
  display: flex;
  flex-wrap: wrap;
  padding-left: 20px;
  padding-right: 20px;
  @include media(sm){
    padding-left: 5px;
    padding-right: 5px;
  }
  li{
    border: 2px solid #000;
    border-radius: 3px;
    text-align: center;
    width: calc(20% - 10px);
    padding-top: 13px;
    padding-bottom: 13px;
    box-sizing: border-box;
    margin: 5px;
    @include media(md){
      width: calc(25% - 10px);
    }
    @include media(sm){
      border-width: 1px;
      padding-top: 10px;
      padding-bottom: 10px;
      width: calc(50% - 10px);
    }
  }
}

// work space

.workspace-gallery{
  display: flex;
  flex-wrap: wrap;
}

.workspace-block{
  margin-bottom: 20px;
  @include media(md-lg){
    width: 50%;
    padding-left: 10px;
    padding-right: 10px;
  }

  &__photo{
    margin-bottom: 20px;
    img{
      border-radius: 10px;
    }
  }

  &__content{
    @include media(md-lg){
      padding-left: 2em;
      padding-right: 2em;
    }
  }
}

.workspace{
  &__titlearea{
    text-align: center;
    margin-bottom: 20px;
  }
}

.workspace-pill{
  text-align: center;
}

// access

.access-panel{
  display: flex;
  background-color: #fff;
  border-radius: 10px;
  @include media(sm){
    flex-direction: column;
  }

  &__content{
    width: 100%;
    padding: 10px;
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 60px 50px;
    @include media(sm){
      padding-top: 30px;
      padding-bottom: 30px;
    }
  }

  &__map{
    width: 100%;
    display: flex;

    iframe{
      width: 100%;
      height: 100%;
      @include media(sm){
        height: 250px;
      }
    }
  }
}

.access-title{
  font-size: 30px;
  margin-bottom: 20px;
}

.access-address{
  font-size: 20px;
  line-height: 1.4;
}

.access-time{
  font-size: 19px;
}

.mb0{
  margin-bottom: 0;
}

.small{
  font-size: 0.8em;
  line-height: 1.8;
}

.access-detail{
  margin-bottom: 2em;
}

.access-footer{
  text-align: center;
}

// contact

.contact-intro{
  @include media(md-lg){
    font-size: 18px;
    text-align: center;
    margin-top: -2em;
    margin-bottom: 2em;
  }
}

.contact-main{
  max-width: 800px;
  margin-left: auto;
  margin-right: auto;
  margin-top: 3em;
}

// animations
// @import "~assets/scss/object/component/animate";

</style>
