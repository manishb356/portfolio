<template>
  <v-app>
    <v-main class="pt-lg-0">
      <Navbar></Navbar>
      <router-view></router-view>
    </v-main>
  </v-app>
</template>

<script>
import Navbar from "@/components/Navbar";

export default {
  name: "App",
  components: { Navbar },
  data: () => ({}),
};
</script>

<style>
html {
  font-size: 1.15rem;
}

.display {
  min-height: 100vh;
  margin: 0;
  font-family: "Kumbh Sans", sans-serif;
}

h1,
h2,
h3,
h4 {
  font-family: "Saira Extra Condensed", -apple-system, BlinkMacSystemFont,
    "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif, "Apple Color Emoji",
    "Segoe UI Emoji", "Segoe UI Symbol", "Noto Color Emoji";
  text-transform: uppercase;
  margin-bottom: 1rem;
}

h1 {
  font-weight: 800;
  font-size: 5.4rem;
  line-height: 5.4rem;
  color: #ffc900;
}
h2 {
  font-weight: 700;
  font-size: 4rem;
  line-height: 4rem;
  color: #ffc900;
}
h3 {
  font-weight: 400;
  font-size: 2rem;
  line-height: 2rem;
}

h4 {
  font-weight: 300;
  font-size: 1.75rem;
  line-height: 1.75rem;
}
</style>
