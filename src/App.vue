<template>
  <v-app>
    <LoginForm></LoginForm>
  </v-app>
</template>

<script>
import LoginForm from "@/components/LoginForm.vue";

export default {
  name: "App",

  data: () => ({
    //
  }),

  components: {
    LoginForm
  }
};
</script>
