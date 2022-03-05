<template>
  <v-app>
    <v-app-bar dark color="orange" :clipped-left="clipped" fixed app>
      <v-icon class="mx-2" @click="back">mdi-cloud-outline</v-icon>
      <v-toolbar-title @click="back" v-text="title" />
      <v-spacer />
    </v-app-bar>
    <v-main>
      <v-container>
        <nuxt />
      </v-container>
    </v-main>
    <p class="footer">© 2022 MarkingCloud</p>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      clipped: false,
      title: "Portfolio",
    };
  },
  methods: {
    back() {
      this.$router.push("/");
    },
  },
};
</script>

<style>
* {
  font-family: auto;
}

.footer {
  text-align: center;
}
</style>
