<template>
  <v-row justify="center">
    <!-- ここから自分の情報に編集してください -->
    <!-- ヘッダー画像 -->
    <v-img src="/header_img.png" width="100%" height="240" />

    <v-col cols="12" align="center">
      <!-- アイコン画像 -->
      <img
        src="/selfe.jpg"
        width="240"
        height="240"
        class="ma-12 rounded-circle"
      />
      <!-- 自己紹介 -->
      <p class="text-h3">shunkat</p>
      <p class="text-h6 text--secondary mb-12">
        ギリギリ新卒1年目Androidアプリエンジニアです。<br />
        大学3年生の冬の終わりに、インターン先でプログラミングを触り、面白さに気づきました。<br />
        最近はFlutterとVueを触って遊んでいます。<br />
        ハッカソン出場がマイブームなので、どなたか一緒に出場しませんか？
      </p>

      <!-- スキル -->
      <p class="text-h4">スキル</p>
      <p class="text-h6 text--secondary mb-12">Kotlin / Flutter / Ruby on Rails / Vue / AWS</p>

      <!-- 趣味 -->
      <p class="text-h4">趣味</p>
      <p class="text-h6 text--secondary mb-12">ハッカソン出場 / 陶芸 / ツーリング / ダーツ</p>

      <!-- 制作物 -->
      <p class="text-h4">制作物</p>

      <v-row class="ma-12">
        <v-col
          cols="4"
          class="px-12"
          v-for="content in contents.contents"
          :key="content.id"
        >
          <nuxt-link :to="`/works/${content.id}/`">
            <v-card elevation="2" outlined>
              <v-card-title>{{ content.title }}</v-card-title>
              <v-img :src="content.capture.url" height="240" />
            </v-card>
          </nuxt-link>
        </v-col>
      </v-row>
    </v-col>

    <div class="button-area">
      <nuxt-link to="/contact/" class="button">お問い合わせ</nuxt-link>
    </div>
  </v-row>
</template>

<script>
export default {
  async asyncData({ $microcms }) {
    const contents = await $microcms.get({
      endpoint: "products",
    });
    return {
      contents,
    };
  },
};
</script>
