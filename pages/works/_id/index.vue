<template>
  <div class="child">
    <h1 class="title">{{ product.title }}</h1>
    <div class="productWrapper">
        <figure class="capture">
            <img
                :width="260"
                :height="260"
                :src="product.capture.url"
                :alt="product.title"
            />        
        </figure>

        <div class="detail">
            <h3>概要</h3>
            <div class="overView">{{ product.overview }}</div>
            <h4>url</h4>
            <div class="url">{{ product.url }}</div>
            <h4>使用技術</h4>
            <div class="tech">{{ product.tech }}</div>
            <h4>果たした役割</h4>
            <div class="role">{{ product.role }}</div>
        </div>
    </div>
    <p class="button-area">
      <nuxt-link to="/">back</nuxt-link>
    </p>
  </div>


</template>

<style lang="css" scoped>
.productWrapper {
    display: flex;
    padding: 20px;
    background-color: orange;
}
</style>

<script>
export default {
  async asyncData({ $microcms, params }) {
    const product = await $microcms.get({
      endpoint: `products/${params.id}`,
    })
    return {
      product,
    }
  },
}
</script>


