<template>
  <v-container fluid class="about pa-0">
    <v-responsive>
      <v-row align="center" justify="center" class="display">
        <v-col cols="11">
          <h1>Manish <span class="white--text">B</span></h1>
          <div class="mb-7">
            Fullstack WebDev · Flutter · Blockchain Enthusiast ·
            <a href="mailto:manishbasavalinga356@gmail.com?subject=Hey There"
              >Email</a
            >
          </div>
          <div class="my-7">
            I am experienced in Vue.js and Flutter in which I produce high
            quality code that are both well performing and well tested. I focus
            on solving problems, not only technical problems but creating an
            awesome experience for the users of my software both visual and
            accessible. Mixing powerful tools and knowledge about the users
            brings visual UI's to life and leads to webpages being accessible
            and useful.
          </div>
          <div class="my-7">
            You can download my resume
            <a href="./resume.pdf" target="_blank">here</a>
          </div>
          <v-row class="my-7">
            <v-btn
              fab
              v-for="link in infoList"
              :key="link.name"
              :href="link.link"
              target="_BLANK"
            >
              <v-icon>{{ link.name }}</v-icon>
            </v-btn>
          </v-row>
        </v-col>
      </v-row>
    </v-responsive>
  </v-container>
</template>

<script>
export default {
  name: "About",
  data: () => ({
    infoList: [
      {
        name: "mdi-linkedin",
        link: "https://www.linkedin.com/in/manish-b-726324192/",
      },
      {
        name: "mdi-github",
        link: "https://github.com/ManishBasavalinga/",
      },
      {
        name: "fab fa-dev",
        link: "https://dev.to/manishb356",
      },
    ],
  }),
};
</script>

<style scoped>
.v-btn {
  margin-right: 8px;
  margin-left: 8px;
}
</style>
