<template>
  <v-app-bar color="white">
    <v-icon color="red" large>mdi-pinterest</v-icon>
    <router-link to="/"><v-btn rounded text large>홈</v-btn></router-link>
    <router-link to="/"><v-btn rounded text large>팔로잉</v-btn></router-link>
    <v-text-field
      placeholder="검색"
      prepend-inner-icon="mdi-magnify"
      hide-details
      filled
      rounded
      dense
    ></v-text-field>
    <v-btn icon><v-icon>mdi-bell</v-icon></v-btn>
    <v-btn icon><v-icon>mdi-chat-processing</v-icon></v-btn>
    <v-avatar color="#efefef" size="40">TG</v-avatar>
    <v-btn icon><v-icon>mdi-chevron-down</v-icon></v-btn>
  </v-app-bar>
</template>

<script>
export default {
  name: "AppBar"
};
</script>

<style lang="scss" scoped>
</style>