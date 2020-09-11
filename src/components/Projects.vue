<template>
  <v-container fluid class="projects pa-0">
    <v-responsive>
      <v-row align="center" justify="center" class="display">
        <v-col cols="11">
          <h2>Projects</h2>
          <v-row justify="center">
            <v-col
              cols="10"
              sm="6"
              lg="4"
              xl="3"
              v-for="index in displayCount"
              :key="index"
            >
              <v-card>
                <v-card-title
                  v-text="responses[index - 1].name"
                  class="secondary--text"
                ></v-card-title>
                <v-card-subtitle
                  >Created At:
                  {{ responses[index - 1].created_at }}</v-card-subtitle
                >
                <v-card-text
                  v-text="responses[index - 1].description"
                ></v-card-text>
                <v-card-actions>
                  <v-spacer></v-spacer>
                  <v-btn icon target="_BLANK" :href="responses[index - 1].url"
                    ><v-icon>mdi-open-in-new</v-icon></v-btn
                  >
                </v-card-actions>
              </v-card>
            </v-col>
          </v-row>
          <v-row justify="center" v-if="displayCount < responses.length">
            <v-btn outlined color="primary" @click="showFull = true"
              >Load More</v-btn
            >
          </v-row>
        </v-col>
      </v-row>
    </v-responsive>
  </v-container>
</template>

<script>
import axios from "axios";
export default {
  name: "Projects",
  data: () => ({
    responses: [],
    showFull: false,
  }),

  created() {
    axios
      .get("https://api.github.com/users/ManishBasavalinga/repos")
      .then((response) => {
        response.data.forEach((element) => {
          this.responses.push({
            name: element.name,
            created_at: element.created_at.slice(0, 10),
            description: element.description,
            url: element.html_url,
          });
        });
      });
  },
  computed: {
    displayCount() {
      if (this.showFull) {
        return this.responses.length;
      } else {
        switch (this.$vuetify.breakpoint.name) {
          case "xs":
            return this.responses.length <= 3 ? this.responses.length : 3;
          case "sm":
            return this.responses.length <= 4 ? this.responses.length : 4;
          case "md":
            return this.responses.length <= 4 ? this.responses.length : 4;
          case "lg":
            return this.responses.length <= 6 ? this.responses.length : 6;
          case "xl":
            return this.responses.length <= 8 ? this.responses.length : 8;
          default:
            return this.responses.length <= 8 ? this.responses.length : 8;
        }
      }
    },
  },
};
</script>
