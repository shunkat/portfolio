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
    <!-- ここから自分の情報に編集してください -->
    <section id="introduction" class="primary">
      <div class="container">
        <h2 class="middleTitle">自己紹介</h2>
        <div class="profile">
          <h1 class="name">＜名前をここに＞</h1>
          <div class="tech">
            <h3>技術領域</h3>
            <p>＜技術スタックをここに＞</p>
          </div>
          <div class="hobby">
            <h3>趣味</h3>
            <p>＜趣味をここに＞</p>
          </div>
          <figure class="selfee">
            <img src="https://placehold.jp/260x260.png" alt="your name" />
          </figure>
          <p class="detailintroduction">
            ＜こまかい自己紹介はここに入れてみましょう＞<br />
            例えば、どうしてエンジニアになったのかorなりたいのかなど<br />
            もし思いつかなければ好きなご飯のおかずを書いてください。
          </p>
        </div>
      </div>
    </section>
    <!-- ここまで編集 -->

    <section id="works" class="primary">
      <div class="container">
        <h2 class="middleTitle">制作物</h2>
        <!-- ここからコメントアウト外す -->
        <div class="products">
          <div v-for="content in contents.contents" :key="content.id" class="eachProduct">
            <nuxt-link :to="`/works/${content.id}/`" class="productWrapper">
              <div class="title">
                <p class="works__name">{{ content.title }}</p>
              </div>
              <figure class="productImage">
                <img
                  :width="260"
                  :height="260"
                  :src="content.capture.url"
                  :alt="content.title"
                />
              </figure>
            </nuxt-link>
          </div>
        </div>
        <!-- ここまでコメントアウト外す -->
        <p class="button-area">
          <nuxt-link to="/contact/" class="button">お問い合わせ</nuxt-link>
        </p>
      </div>
    </section>
  </div>
</template>

<style lang="css" scoped>
.mainVisual img {
  width: 100%;
}
.products{
  display: flex;
}
</style>

<script>
export default {
  async asyncData({ $microcms }) {
    const contents = await $microcms.get({
      endpoint: 'products',
      queries: { limit: 2 },
    })
    return {
      contents,
    }
  },
}
</script>
