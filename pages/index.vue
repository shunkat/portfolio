<template>
  <div>
    <div class="mainVisual">
      <picture>
        <source
          srcset="https://placehold.jp/375x530.png"
          media="(max-width: 767px)"
        />
        <img src="https://placehold.jp/1440x436.png" alt="" />
      </picture>
    </div>

    <section id="about" class="sectionPrimary">
      <div class="container">
        <h2 class="headingPrimary">about</h2>
        <div class="profile">
          <div class="profile__upper">
            <div class="profile__text">
              <p class="profile__name">
                加藤　竣<span lang="en">Shun Kato</span>
              </p>
              <dl class="profile__item">
                <dt class="profile__title">技術スタック</dt>
                <dd>HTML / CSS / jQuery / JavaScript / Nuxt</dd>
              </dl>
              <dl class="profile__item">
                <dt class="profile__title">趣味</dt>
                <dd>開発、陶芸、競技ダンス、登山、映画鑑賞</dd>
              </dl>
            </div>
            <figure class="profile__image">
              <img src="https://placehold.jp/260x260.png" alt="your name" />
            </figure>
          </div>
          <p class="profile__message">
            自己紹介を入れましょう。出身や経歴と現在の仕事の内容を簡単に話すも良し。<br />数年後の目標や今学んでいること、活動している内容を入れるのも良いかと思います。
          </p>
        </div>
      </div>
    </section>

    <section class="sectionPrimary background--gray">
      <div class="container">
        <h2 class="headingPrimary">works</h2>
        <ol class="row works">
          <li class="works__item">
            <nuxt-link to="#!" class="works__inner">
              <figure class="works__image">
                <img src="https://placehold.jp/370x229.png" alt="" />
              </figure>
              <div class="works__text">
                <p class="works__name">作品名</p>
                <p class="works__date">
                  <time datetime="2021-12-16">2021.12.16</time>
                </p>
              </div>
            </nuxt-link>
          </li>
          <li class="works__item">
            <nuxt-link to="#!" class="works__inner">
              <figure class="works__image">
                <img src="https://placehold.jp/370x229.png" alt="" />
              </figure>
              <div class="works__text">
                <p class="works__name">作品名</p>
                <p class="works__date">
                  <time datetime="2021-12-16">2021.12.16</time>
                </p>
              </div>
            </nuxt-link>
          </li>
        </ol>
        <p class="button-area">
          <nuxt-link to="/works" class="buttonPrimary">view more</nuxt-link>
        </p>
      </div>
    </section>
  </div>
</template>

<style lang="css" scoped>
.mainVisual {
  img {
    width: 100%;
  }
}
</style>