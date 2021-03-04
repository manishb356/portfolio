<template>
  <v-container fluid class="experience pa-0">
    <v-responsive>
      <v-row align="center" justify="center" class="display mx-2">
        <v-col cols="11">
          <h2>Experience</h2>
          <v-timeline class="mt-6 pt-0">
            <v-timeline-item
              v-for="(entry, i) in experiences"
              :key="i"
              :color="entry.color"
              small
            >
              <template v-slot:opposite>
                <h4 :class="`${entry.color}--text`" v-text="entry.year"></h4>
              </template>
              <div class="py-4">
                <h4 :class="`mb-4 ${entry.color}--text`">
                  {{ entry.title }}
                </h4>
                <div>{{ entry.description }}</div>
              </div>
            </v-timeline-item>
          </v-timeline>
        </v-col>
      </v-row>
    </v-responsive>
  </v-container>
</template>

<script>
export default {
  name: "Experience",
  data: () => ({
    experiences: [
      {
        color: "cyan",
        year: "Aug 2020 - Sep 2020",
        title: "Research Intern at Rank Technologies",
        description:
          "Helped in establishing compatibility with third-party software products by testing different APIs with Postman.",
      },
      {
        color: "red",
        year: "Oct 2020 - Feb 2021",
        title: "Web Development Intern at PolicyEra",
        description:
          "Built the Web-App for the CRM Software. Implemented Authentication Dashboard and Profile Management.",
      },
    ],
  }),
};
</script>
