<template>
  <div class="child">
    <div class="productWrapper">
        <h1 class="title">作品名</h1>
        <p>
        google つくりました。詳細説明はここらへんに
        </p>
        <figure class="capture">
            <img src="/google.png" width=260 height=260 alt="" />
        </figure>

        <div class="detail">
            <div class="overView">詳細説明はここに</div>
            <div class="url">urlはここに</div>
            <div class="tech">使用技術はここに</div>
            <div class="role">自分が果たした役割はここに</div>
        </div>
    </div>
    <p class="button-area">
      <nuxt-link to="/">back</nuxt-link>
    </p>
  </div>
</template>
