<template>
  <v-row justify="center">
    <!-- ここから自分の情報に編集してください -->
    <!-- ヘッダー画像 -->
    <v-img src="/header_img.png" width="100%" height="240" />

    <v-col cols="12" align="center">
      <!-- アイコン画像 -->
      <img
        src="/yourIcon.jpg"
        width="240"
        height="240"
        class="ma-12 rounded-circle"
      />
      <!-- 自己紹介 -->
      <p class="text-h3">「1. 名前」</p>
      <p class="text-h6 text--secondary mb-12">
        「2. 細かい自己紹介」<br />
        例えば、どうしてエンジニアになったのか or なりたいのかなど。<br />
        もし思いつかなければ好きなご飯のおかずを書いてください。
      </p>

      <!-- スキル -->
      <p class="text-h4">スキル</p>
      <p class="text-h6 text--secondary mb-12">「3. 技術スタック」</p>

      <!-- 趣味 -->
      <p class="text-h4">趣味</p>
      <p class="text-h6 text--secondary mb-12">「4. 趣味」</p>

      <!-- 制作物 -->
      <p class="text-h4">制作物</p>
      <v-row class="ma-12">

      <!-- この下からコメントアウト外す：「コードミッション1」 -->
        <!-- <v-col cols="4" class="px-12"
          v-for="content in contents.contents" :key="content.id">
          <nuxt-link :to="``">
            <v-card elevation="2" height="200">
              <v-card-title>{{ content.title }}</v-card-title>
              <v-img :src="content.capture.url" height="240" />
            </v-card>
          </nuxt-link> 
        </v-col> -->
      <!-- この上までコメントアウト外す -->

      </v-row>
    </v-col>

    <div class="button-area">
      <nuxt-link to="/contact/" class="button">お問い合わせ</nuxt-link>
    </div>
  </v-row>
</template>

<script>
// ここから削除：コードミッション4
export default {
  data() {
    return { contents: 
    {contents:
      [
        // サンプルデータ群
        {id:1,title:'sample1',url:'',overview:'',url:'',tech:'',role:'',capture:{url:'1.png'}},
        {id:2,title:'sample2',url:'',overview:'',url:'',tech:'',role:'',capture:{url:'2.png'}},
        {id:3,title:'sample3',url:'',overview:'',url:'',tech:'',role:'',capture:{url:'3.png'}},
      ]
    }
    };
  }
}
// ここまで削除

// この下からコメントアウト外す：コードミッション4
// export default {
//   async asyncData({ $microcms }) {
//     const contents = await $microcms.get({
//       endpoint: "contents",
//     });
//     return {
//       contents,
//     };
//   },
// };
// この上までコメントアウト外す
</script>
