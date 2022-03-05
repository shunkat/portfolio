<template>
  <v-row justify="center" align-content="center" class="mx-16">
    <v-col cols="12" align="center">
      <v-spacer class="my-16" />
      <v-row>
        <!-- 画像 -->
        <v-col cols="6" align="right">
          <v-img contain height="300" :src="product.capture.url" />
        </v-col>

        <!-- タイトル・概要 -->
        <v-col cols="6" align="left" class="my-8">
          <p class="text-h3 mb-8">{{ product.title }}</p>
          <p class="text-h6 text--primary">{{ product.overview }}</p>
        </v-col>
      </v-row>
      <v-spacer class="my-16" />

      <!-- 概要 -->
      <p class="text-h5">URL</p>
      <a :href="product.url">
        <p class="text-h6 text--secondary mb-12">{{ product.url }}</p>
      </a>

      <!-- 使用技術 -->
      <p class="text-h5">使用技術</p>
      <p class="text-h6 text--secondary mb-12">{{ product.tech }}</p>

      <!-- 果たした役割 -->
      <p class="text-h5">果たした役割</p>
      <p class="text-h6 text--secondary mb-12">{{ product.role }}</p>
    </v-col>

    <p class="button-area">
      <nuxt-link to="/">back</nuxt-link>
    </p>
  </v-row>
</template>

<script>
export default {
  async asyncData({ $microcms, params }) {
    const product = await $microcms.get({
      endpoint: `contents/${params.id}`,
    });
    return {
      product,
    };
  },
};
</script>
