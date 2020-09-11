<template>
  <v-container fluid class="skills pa-0">
    <v-responsive>
      <v-row align="center" justify="center" class="display">
        <v-col cols="11">
          <h2>Skills</h2>

          <h3>Languages:</h3>
          <v-row justify="start" class="pb-5">
            <v-tooltip bottom v-for="link in languagesLinks" :key="link.name">
              <template v-slot:activator="{ on, attrs }">
                <v-avatar v-bind="attrs" v-on="on" class="mx-1">
                  <img :src="link.link" />
                </v-avatar>
              </template>
              <span v-text="link.name"></span>
            </v-tooltip>
          </v-row>
          <h3>Tools:</h3>
          <v-row justify="start">
            <v-tooltip bottom v-for="link in toolsLinks" :key="link.name">
              <template v-slot:activator="{ on, attrs }">
                <v-avatar v-bind="attrs" v-on="on" class="mx-1">
                  <img :src="link.link" />
                </v-avatar>
              </template>
              <span v-text="link.name"></span>
            </v-tooltip>
          </v-row>
        </v-col>
      </v-row>
    </v-responsive>
  </v-container>
</template>

<script>
export default {
  name: "Skills",
  data: () => ({
    languagesLinks: [
      {
        link: "https://img.icons8.com/color/48/000000/html-5.png",
        name: "Html 5",
      },
      {
        link: "https://img.icons8.com/color/48/000000/css3.png",
        name: "Css 3",
      },
      {
        link: "https://img.icons8.com/color/48/000000/c-plus-plus-logo.png",
        name: "C++",
      },
      {
        link: "https://img.icons8.com/color/48/000000/java-coffee-cup-logo.png",
        name: "Java",
      },
      {
        link: "https://img.icons8.com/color/48/000000/python.png",
        name: "Python",
      },
      { link: "https://img.icons8.com/color/48/000000/dart.png", name: "Dart" },
      {
        link: "https://img.icons8.com/color/48/000000/ethereum.png",
        name: "Solidity",
      },
    ],
    toolsLinks: [
      {
        link: "https://img.icons8.com/color/48/000000/vue-js.png",
        name: "Vue JS",
      },
      {
        link: "https://img.icons8.com/officel/48/000000/react.png",
        name: "React Js",
      },
      {
        link: "https://img.icons8.com/color/48/000000/nodejs.png",
        name: "Node Js",
      },
      {
        link: "https://img.icons8.com/color/48/000000/flutter.png",
        name: "Flutter",
      },
      {
        link: "https://img.icons8.com/color/48/000000/mongodb.png",
        name: "MongoDB",
      },
      {
        link: "https://img.icons8.com/color/48/000000/firebase.png",
        name: "Firebase",
      },
      {
        link: "https://img.icons8.com/color/48/000000/postgreesql.png",
        name: "PostgreSQL",
      },
      {
        link: "https://img.icons8.com/ultraviolet/40/000000/api-settings.png",
        name: "Rest API",
      },
    ],
  }),
};
</script>
