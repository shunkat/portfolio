<template>
  <div>
    <!-- ここから自分の情報に編集してください -->
    <section id="introduction" class="primary">
      <div class="container">
        <div class="profile">
          <h2 class="middleTitle">自己紹介</h2>
          <h1 class="name">＜名前をここに＞</h1>
          <div class="tech">
            <h3>技術領域</h3>
            <p>＜技術スタックをここに＞</p>
          </div>
          <div class="hobby">
            <h3>趣味</h3>
            <p>＜趣味をここに＞</p>
          </div>
          <h3>どんな人</h3>
          <p class="detailintroduction">
            ＜こまかい自己紹介はここに入れてみましょう＞<br />
            例えば、どうしてエンジニアになったのかorなりたいのかなど<br />
            もし思いつかなければ好きなご飯のおかずを書いてください。
          </p>
        </div>
        <figure class="selfee">
          <img src="/yourIcon.jpg" width=260 height=260 alt="your name" />
        </figure>
      </div>
    </section>
    <!-- ここまで編集 -->

    <section id="works" class="primary">
      <div class="container">
        <h2 class="middleTitle">制作物</h2>
        <!-- ここからコメントアウト外す -->
        <!-- <div class="products">
          <div v-for="content in contents.contents" :key="content.id" class="eachProduct">
            <nuxt-link :to="`/works/${content.id}/`">
              <div class="productWrapper">
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
              </div>
            </nuxt-link>
          </div>
        </div> -->
        <!-- ここまでコメントアウト外す -->
        <!-- ここからコメントアウト -->
        <div class="products">
          <div class="eachProduct">
            <nuxt-link :to="`/works/`">
              <div class="productWrapper">
                <div class="title">
                <p class="productTitle">サンプルプロダクト</p>
                </div>
                <figure class="productImage">
                  <img width="260" height="260" src="/markingCloud.png" alt="sampleImageOfProduct" />
                </figure>
              </div>
            </nuxt-link>
          </div>
          <div class="eachProduct">
            <nuxt-link :to="`/works/`">
              <div class="productWrapper">
                <div class="title">
                <p class="productTitle">サンプルプロダクト2</p>
                </div>
                <figure class="productImage">
                  <img width="260" height="260" src="/isoroot_logo.png" alt="sampleImageOfProduct" />
                </figure>
              </div>
            </nuxt-link>
          </div>
          <div class="eachProduct">
            <nuxt-link :to="`/works/`">
              <div class="productWrapper">
                <div class="title">
                <p class="productTitle">サンプルプロダクト3</p>
                </div>
                <figure class="productImage">
                  <img width="260" height="260" src="/google.png" alt="sampleImageOfProduct" />
                </figure>
              </div>
            </nuxt-link>
          </div>
        </div>
      </div>
      
    </section>
    <div class="button-area">
          <nuxt-link to="/contact/" class="button">お問い合わせ</nuxt-link>
      </div>
  </div>
</template>

<style lang="css" scoped>
body {
  width: 1250px;
}
.mainVisual img {
  width: 100%;
}

.container {
  display: flex;
  flex-wrap: wrap;
}
#works {
  background-color: orange;
}
.products{
  display: flex;
  flex-wrap: wrap;
  justify-content: center;

}
.eachProduct{
  width: 50%;
}
.productWrapper{
  display: flex;
  flex-wrap: wrap;
}
img {
  display: block;
  margin-left: auto;
  margin-right: auto 
}
</style>

<script>
export default {
  async asyncData({ $microcms }) {
    const contents = await $microcms.get({
      endpoint: 'products'
    })
    return {
      contents,
    }
  },
}
</script>
