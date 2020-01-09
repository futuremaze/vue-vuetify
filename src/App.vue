<template>
  <v-app>
    <!-- app: 高さの自動調整 -->
    <!-- clipped: ナビゲーションメニューをナビゲーションバーの下に表示する -->
    <v-navigation-drawer app v-model="drawer" clipped>
      Navigation Lists
    </v-navigation-drawer>
    <!-- color: 背景色指定 primary: デフォルト(水色) -->
    <!-- dark: 文字色が白に -->
    <!-- app: 高さの自動調整 -->
    <!-- clipped-left: ナビゲーションメニューをナビゲーションバーの下に表示する -->
    <v-app-bar color="primary" dark app clipped-left>
      <!-- v-app-bar-nav-icon: ハンバーガーメニューアイコン -->
      <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>
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
    drawer: null
  })
};
</script>
