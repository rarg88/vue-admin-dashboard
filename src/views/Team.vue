<template>
  <div class="container">
    <h2>Equipo</h2>
    <div class="cards">
      <a
        class="card animate__animated animate__flipInX card-1"
        :class="{ 'light-card': !isDarkMode, 'dark-card': isDarkMode }"
        ><img
          src="@/assets/slack.png"
          class="card-header"
          :class="{ 'light-header': !isDarkMode, 'dark-header': isDarkMode }"
        />
        <h3 :class="{ 'light-text': isDarkMode, 'dark-text': !isDarkMode }">
          Slack
        </h3>
        <p :class="{ 'light-text': isDarkMode, 'dark-text': !isDarkMode }">
          App de mensajería para las comunicaciones de todo el equipo.
        </p>
      </a>
      <a
        class="card animate__animated animate__flipInX card-2"
        :class="{ 'light-card': !isDarkMode, 'dark-card': isDarkMode }"
        ><img
          src="@/assets/notion.png"
          class="card-header"
          :class="{ 'light-header': !isDarkMode, 'dark-header': isDarkMode }"
        />
        <h3 :class="{ 'light-text': isDarkMode, 'dark-text': !isDarkMode }">
          Notion
        </h3>
        <p :class="{ 'light-text': isDarkMode, 'dark-text': !isDarkMode }">
          Espacio de trabajo todo en uno.
        </p></a
      >
      <a
        class="card animate__animated animate__flipInX card-3"
        :class="{ 'light-card': !isDarkMode, 'dark-card': isDarkMode }"
        ><img
          src="@/assets/figma.png"
          class="card-header"
          :class="{ 'light-header': !isDarkMode, 'dark-header': isDarkMode }"
        />
        <h3 :class="{ 'light-text': isDarkMode, 'dark-text': !isDarkMode }">
          Figma
        </h3>
        <p :class="{ 'light-text': isDarkMode, 'dark-text': !isDarkMode }">
          Herramiento de diseño colaborativa.
        </p></a
      >
      <a
        class="card animate__animated animate__flipInX card-4"
        :class="{ 'light-card': !isDarkMode, 'dark-card': isDarkMode }"
        ><img
          src="@/assets/contentful.png"
          class="card-header"
          :class="{ 'light-header': !isDarkMode, 'dark-header': isDarkMode }"
        />
        <h3 :class="{ 'light-text': isDarkMode, 'dark-text': !isDarkMode }">
          Contentful
        </h3>
        <p :class="{ 'light-text': isDarkMode, 'dark-text': !isDarkMode }">
          Sistema de administración de contenido.
        </p></a
      >
      <a
        class="card animate__animated animate__flipInX card-5"
        :class="{ 'light-card': !isDarkMode, 'dark-card': isDarkMode }"
        ><img
          src="@/assets/dropbox.png"
          class="card-header"
          :class="{ 'light-header': !isDarkMode, 'dark-header': isDarkMode }"
        />
        <h3 :class="{ 'light-text': isDarkMode, 'dark-text': !isDarkMode }">
          Dropbox
        </h3>
        <p :class="{ 'light-text': isDarkMode, 'dark-text': !isDarkMode }">
          Espacio de almacenamiento en la nube.
        </p></a
      >
    </div>
  </div>
</template>

<script>
export default {
  name: "Team",
  computed: {
    isDarkMode() {
      return this.$store.getters.isDarkMode;
    },
  },
};
</script>

<style scoped lang="scss">
.container {
  margin-left: 25px;
}

.cards {
  display: flex;
  flex-wrap: wrap;
  justify-content: flex-start;
  align-items: space-evenly;
}

.card {
  height: 400px;
  width: 100%;
  max-width: 300px;
  border-radius: 10px;
  background-color: red;
  margin: 20px;
}

.card-1 {
  animation-delay: 0s;
}
.card-2 {
  animation-delay: 0.5s;
}
.card-3 {
  animation-delay: 1s;
}
.card-4 {
  animation-delay: 1.5s;
}
.card-5 {
  animation-delay: 2s;
}

.card-header {
  width: 100%;
  border-radius: 10px 10px 0 0;
}

.light-header {
  background: $light-gray;
}

.dark-header {
  background: #283049;
}

h3 {
  @include heading-3;
  margin-bottom: 16px;
}

p {
  font-size: 15px;
  line-height: 24px;
  text-align: left;
  margin-left: 16px;
  margin-top: 0;
}

.light-card {
  background-color: $white;
  box-shadow: 0px 20px 40px rgba(0, 0, 0, 0.15);
  &:hover {
    box-shadow: 0px 30px 60px rgba(0, 0, 0, 0.35);
  }
}

.dark-card {
  background-color: $super-dark-blue;
  box-shadow: 0px 20px 40px rgba(255, 255, 255, 0.15);
  &:hover {
    box-shadow: 0px 30px 60px rgba(255, 255, 255, 0.35);
  }
}
</style>