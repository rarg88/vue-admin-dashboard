<template>
  <div
    v-show="show"
    class="request animate__animated animate__slideInRight"
    :class="{ 'light-request': isDarkMode, 'dark-request': !isDarkMode }"
  >
    ¿No tienes una cuenta?
    <router-link to="/request">Solicita una cuenta</router-link>
  </div>
</template>

<script>
export default {
  name: "RequestAccount",
  data() {
    return {
      show: false,
    };
  },
  mounted() {
    this.show = true;
  },
  computed: {
    isDarkMode() {
      return this.$store.getters.isDarkMode;
    },
  },
};
</script>

<style lang="scss" scoped>
.request {
  position: absolute;
  top: 40px;
  right: 40px;
}

.light-request {
  color: rgba(255, 255, 255, 0.3);
  a {
    color: $white;
  }
}

.dark-request {
  color: rgba(0, 0, 0, 0.3);

  a {
    color: $black;
  }
}
</style>