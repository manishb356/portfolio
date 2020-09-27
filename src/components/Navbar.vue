<template>
  <div>
    <v-app-bar
      dense
      class="d-block d-md-none"
      app
      fixed
      elevate-on-scroll
      scroll-threshold="70"
    >
      <div @click="programaticallyScroll('About')">
        <v-avatar color="grey" size="35">
          <v-img :src="require('../assets/logo.png')"></v-img>
        </v-avatar>
      </div>
    </v-app-bar>
    <v-navigation-drawer fixed app mobile-breakpoint="960">
      <v-container class="fill-height" fluid>
        <v-row>
          <v-col>
            <v-row align="center" justify="center" class="pb-4">
              <v-avatar color="grey" size="164">
                <v-img :src="require('../assets/profile.jpg')"></v-img>
              </v-avatar>
            </v-row>

            <v-row
              v-for="link in links"
              :key="link"
              align="center"
              justify="center"
              class="py-1"
            >
              <v-btn
                elevation="0"
                class="no-background-hover"
                :ripple="false"
                text
                @click="programaticallyScroll(link)"
                >{{ link }}</v-btn
              >
            </v-row>
          </v-col>
        </v-row>
      </v-container>
    </v-navigation-drawer>
    <v-footer absolute padless color="transparent">
      <v-col class="text-end" cols="12">
        Icons from <a href="https://icons8.com/" target="_BLANK">icons8</a>
      </v-col>
    </v-footer>
  </div>
</template>

<script>
export default {
  name: "Navbar",
  data: () => ({
    pressedLink: "",
    links: ["About", "Skills", "Projects", "Experience", "Contact"],
  }),
  methods: {
    programaticallyScroll(value) {
      this.pressedLink = value.toLowerCase();
      this.$vuetify.goTo(this.target, { duration: 500 });
    },
  },
  computed: {
    target() {
      return `.${this.pressedLink}`;
    },
  },
};
</script>

<style lang="scss">
.no-background-hover::before {
  background-color: transparent !important;
}
</style>

<style scoped>
.main-title {
  font-family: "Italianno", cursive;
  font-size: 2rem;
}

button:hover {
  color: #ffc900;
}
</style>
