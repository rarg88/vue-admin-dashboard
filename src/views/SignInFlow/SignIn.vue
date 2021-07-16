<template>
  <div
    class="container"
    :class="{ 'light-background': !isDarkMode, 'dark-background': isDarkMode }"
  >
    <Notification v-if="hasText" :text="text" />
    <RequestAccount />
    <div class="login">
      <img src="@/assets/DCHQ.svg" v-show="isDarkMode" />
      <img src="@/assets/DCHQ-dark.svg" v-show="!isDarkMode" />
      <h4 :class="{ 'light-text': isDarkMode, 'dark-text': !isDarkMode }">
        Regístrate en Desing+Code HQ
      </h4>
      <form @submit.prevent="onSubmit">
        <input
          type="email"
          v-model="email"
          placeholder="Email"
          required
          :class="{ 'light-field': isDarkMode, 'dark-field': !isDarkMode }"
        />
        <input
          type="password"
          placeholder="Password"
          v-model="password"
          required
          :class="{ 'light-field': isDarkMode, 'dark-field': !isDarkMode }"
        />
        <button>Regístrate</button>
      </form>
      <router-link
        to="/recover"
        :class="{ 'light-link': isDarkMode, 'dark-link': !isDarkMode }"
        >¿Has olvidado tu contraseña?</router-link
      >
      <ThemeSwitch />
    </div>
  </div>
</template>

<script>
import RequestAccount from "@/components/RequestAccount";
import ThemeSwitch from "@/components/ThemeSwitch";
import Notification from "@/components/Notification";
import { auth } from "@/main.js";

export default {
  name: "SingIn",
  components: {
    RequestAccount,
    ThemeSwitch,
    Notification,
  },
  data() {
    return {
      email: null,
      password: null,
      hasText: false,
      text: "",
    };
  },

  computed: {
    isDarkMode() {
      return this.$store.getters.isDarkMode;
    },
  },
  methods: {
    onSubmit() {
      const email = this.email;
      const password = this.password;

      auth
        .login(email, password, true)
        .then(() => {
          this.$router.replace("/");
        })
        .catch((error) => {
          alert("Error: " + error);
        });
    },
  },
  mounted() {
    const params = this.$route.params;

    if (params.userLoggedOut) {
      this.hasText = true;
      this.text = "¡Desconectado correctamente!";
    }
  },
};
</script>

<style lang="scss" scoped>
.container {
  display: flex;
  justify-content: center;
  align-items: center;

  min-height: 100vh;
}

.login {
  width: 400px;
}
</style>