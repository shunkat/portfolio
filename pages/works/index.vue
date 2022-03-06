<template>
  <v-row justify="center" align-content="center" class="mx-16">
    <v-col cols="12" align="center">
      <v-spacer class="my-16" />
      <v-row>
        <!-- 画像 -->
        <v-col cols="6" align="right">
          <v-img contain height="300" src="/1.png" />
        </v-col>

        <!-- タイトル・概要 -->
        <v-col cols="6" align="left" class="my-8">
          <p class="text-h3 mb-8">作品名</p>
          <p class="text-h6 text--primary">
            google つくりました。詳細説明はここらへんに
          </p>
        </v-col>
      </v-row>
      <v-spacer class="my-16" />

      <!-- 概要 -->
      <p class="text-h5">URL</p>
      <p class="text-h6 text--secondary mb-12">urlはここに</p>

      <!-- 使用技術 -->
      <p class="text-h5">使用技術</p>
      <p class="text-h6 text--secondary mb-12">使用技術はここに</p>

      <!-- 果たした役割 -->
      <p class="text-h5">果たした役割</p>
      <p class="text-h6 text--secondary mb-12">自分が果たした役割はここに</p>
    </v-col>

    <p class="button-area">
      <nuxt-link to="/">back</nuxt-link>
    </p>
  </v-row>
</template>
