<template>
  <v-card>
    <v-card-title>
      <h1 class="display-1">ログイン</h1>
    </v-card-title>
    <v-card-text>
      <v-form>
        <v-text-field type="text" prepend-icon="mdi-account-circle" label="ユーザー名" />
        <v-text-field type="password" prepend-icon="mdi-lock" append-icon="mdi-eye-off" label="パスワード" />
        <v-card-actions>
          <v-btn>ログイン</v-btn>
        </v-card-actions>
      </v-form>
    </v-card-text>
  </v-card>
</template>