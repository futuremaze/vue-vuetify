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
      <v-spacer></v-spacer>
      <!-- v-toolbar-items: 囲むことによりアイテムの領域判定がapp-barの高さと同じになる -->
      <v-toolbar-items>
        <v-btn text>For Enterprise</v-btn>
        <v-menu offset-y>
          <template v-slot:activator="{ on }">
            <v-btn v-on="on" text>Support<v-icon>mdi-menu-down</v-icon></v-btn>
          </template>
          <v-list>
            <v-subheader>Get help</v-subheader>
            <v-list-item v-for="support in supports" :key="support.name">
              <v-list-item-icon>
                <v-icon>{{ support.icon }}</v-icon>
              </v-list-item-icon>
              <v-list-item-content>
                <v-list-item-title>{{ support.name }}</v-list-item-title>
              </v-list-item-content>
            </v-list-item>
          </v-list>
        </v-menu>
      </v-toolbar-items>
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
    drawer: null,
    supports: [
      { name: "Consulting and support", icon: "mdi-vuetify" },
      { name: "Discord community", icon: "mdi-discord" },
      { name: "Report a bug", icon: "mdi-bug" },
      { name: "Github issue board", icon: "mdi-github-face" },
      { name: "Stack overview", icon: "mdi-stack-overflow" }
    ]
  })
};
</script>
