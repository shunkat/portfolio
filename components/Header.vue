<template>
  <header class="header">
    <div class="headerContainer">
      <component :is="isTopPage ? 'h1' : 'p'" class="title">
        <nuxt-link to="/">My Portfolio</nuxt-link>
      </component>

      <!-- メニュー -->
      <nav>
        <ul class="menu">
          <li>
            <nuxt-link to="/#about" class="menu__link">about</nuxt-link>
          </li>
          <li>
            <nuxt-link to="/works" class="menu__link">works</nuxt-link>
          </li>
        </ul>
      </nav>
    </div>
  </header>
</template>

<script>
export default {
  computed: {
    // TOPページかどうか
    isTopPage() {
      if (this.$route.name === 'index') return true
      return false
    },
  },
}
</script>

<style lang="css" scoped>
.header {
  width: 100%;
  box-shadow: 0 1px 2px rgba(0, 0, 0, 0.1);
  background-color: blue;
}

.headerContainer {
  padding: 0 1.5em;
  display: flex;
  justify-content: space-between;
  align-items: center;

  @include mq() {
    padding: 0 4em;
  }
}
</style>