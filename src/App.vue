<template>
  <v-app>
    <!-- color: 背景色指定 primary: デフォルト(水色) -->
    <!-- dark: 文字色が白に -->
    <!-- app: 高さの自動調整 -->
    <v-app-bar color="primary" dark app>
      <v-toolbar-title>Vuetify</v-toolbar-title>
    </v-app-bar>
    <!-- color: 背景色指定 primary: デフォルト(水色) -->
    <!-- dark: 文字色が白に -->
    <!-- app: 高さの自動調整 -->
    <v-footer color="primary" dark app>
      Vuetify
    </v-footer>
  </v-app>
</template>

<script>
export default {
  name: "App",

  data: () => ({
    //
  })
};
</script>
