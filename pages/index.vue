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

    <section id="introduction" class="sectionPrimary">
      <div class="container">
        <h2 class="introduction">自己紹介</h2>
        <div class="profile">
          <h1 class="name">加藤　竣</h1>
          <dl class="tech">
            <h3 class="profile__title">技術スタック</h3>
            <dd>HTML / CSS / jQuery / JavaScript / Nuxt</dd>
          </dl>
          <dl class="hobby">
            <dt class="profile__title">趣味</dt>
            <dd>開発、陶芸、競技ダンス、登山、映画鑑賞</dd>
          </dl>
          <figure class="profile__image">
            <img src="https://placehold.jp/260x260.png" alt="your name" />
          </figure>
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
          <li v-for="work in works.contents" :key="work.id" class="works__item">
            <nuxt-link :to="`/works/${work.id}/`" class="works__inner">
              <figure class="works__image">
                <img
                  :width="work.capture.width"
                  :height="work.capture.height"
                  :src="work.capture.url"
                  :alt="work.title"
                />
              </figure>
              <div class="works__text">
                <p class="works__name">{{ work.title }}</p>
                <p class="works__date">
                  <time :datetime="work.release">{{ work.release }}</time>
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
.mainVisual img {
  width: 100%;
}
</style>

<script>
export default {
  async asyncData({ $microcms }) {
    const works = await $microcms.get({
      endpoint: 'works',
      queries: { limit: 2 },
    })
    return {
      works,
    }
  },
}
</script>
