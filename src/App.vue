<template>
  <v-app>
    <!-- app: 高さの自動調整 -->
    <!-- clipped: ナビゲーションメニューをナビゲーションバーの下に表示する -->
    <v-navigation-drawer app v-model="drawer" clipped>
      <v-container>
        <v-list-item>
          <v-list-item-content>
            <!-- grey--text: テキスト文字色をグレーに -->
            <!-- text--darken-2: 色の濃さを変更 -->
            <v-list-item-title class="title grey--text text--darken-2">Navigation Lists</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <v-divider></v-divider>
        <!-- dense, nav: スタイリング調整 -->
        <v-list dense nav>
          <!-- no-action: ネスト化されたメニューの左側にpaddingを設ける -->
          <!-- append-icon: 下の階層がないメニューは矢印アイコンを表示しない -->
          <div v-for="navList in navLists" :key="navList.name">
            <!-- ネストされたメニューがあるメニュー -->
            <v-list-group v-if="navList.lists" :prepend-icon="navList.icon" no-action>
              <template v-slot:activator>
                <v-list-item-content>
                  <v-list-item-title>{{ navList.name }}</v-list-item-title>
                </v-list-item-content>
              </template>
              <v-list-item v-for="list in navList.lists" :key="list" :to="list.link">
                <v-list-item-content>
                  <v-list-item-title>{{ list.name }}</v-list-item-title>
                </v-list-item-content>
              </v-list-item>
            </v-list-group>
            <!-- ネストされたメニューがないメニュー -->
            <v-list-item v-else :prepend-icon="navList.icon" :to="navList.link">
              <v-list-item-icon>
                <v-icon v-text="navList.icon"></v-icon>
              </v-list-item-icon>
              <v-list-item-content>
                <v-list-item-title>{{ navList.name }}</v-list-item-title>
              </v-list-item-content>
            </v-list-item>
          </div>
        </v-list>
      </v-container>
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
        <v-btn text to="/enterprise">For Enterprise</v-btn>
        <v-menu offset-y>
          <template v-slot:activator="{ on }">
            <v-btn v-on="on" text>
              Support
              <v-icon>mdi-menu-down</v-icon>
            </v-btn>
          </template>
          <v-list>
            <v-subheader>Get help</v-subheader>
            <v-list-item v-for="support in supports" :key="support.name" :to="support.link">
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
    <v-content>
      <router-view />
    </v-content>
    <!-- color: 背景色指定 primary: デフォルト(水色) -->
    <!-- dark: 文字色が白に -->
    <!-- app: 高さの自動調整 -->
    <v-footer color="primary" dark app>Vuetify</v-footer>
  </v-app>
</template>

<script>
export default {
  name: "App",

  data: () => ({
    //
    drawer: null,
    supports: [
      {
        name: "Consulting and support",
        icon: "mdi-vuetify",
        link: "/consulting-and-support"
      },
      {
        name: "Discord community",
        icon: "mdi-discord",
        link: "/discord-community"
      },
      {
        name: "Report a bug",
        icon: "mdi-bug",
        link: "/report-a-bug"
      },
      {
        name: "Github issue board",
        icon: "mdi-github-face",
        link: "/guthub-issue-board"
      },
      {
        name: "Stack overview",
        icon: "mdi-stack-overflow",
        link: "/stack-overview"
      }
    ],
    navLists: [
      {
        name: "Getting Started",
        icon: "mdi-speedometer",
        lists: [
          {
            name: "Quick Start",
            link: "/quick-start"
          },
          {
            name: "Pre-made layouts",
            link: "/pre-made-layouts"
          }
        ]
      },
      {
        name: "Customization",
        icon: "mdi-cogs",
        link: "/customization"
      },
      {
        name: "Styles & animations",
        icon: "mdi-palette",
        lists: [
          {
            name: "Colors",
            link: "/colors"
          },
          {
            name: "Content",
            link: "/content"
          },
          {
            name: "Display",
            link: "/display"
          }
        ]
      },
      {
        name: "UI Components",
        icon: "mdi-view-dashboard",
        lists: [
          {
            name: "API explorer",
            link: "/api_explorer"
          },
          {
            name: "Alerts",
            link: "/alerts"
          }
        ]
      },
      {
        name: "Directives",
        icon: "mdi-function",
        link: "/directives"
      },
      {
        name: "Premium themes",
        icon: "mdi-vuetify",
        link: "premium-themes"
      }
    ]
  })
};
</script>
