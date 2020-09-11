<template>
  <div>
    <About></About>
    <v-divider></v-divider>
    <Skills></Skills>
    <v-divider></v-divider>
    <Projects></Projects>
    <v-divider></v-divider>
    <Experience></Experience>
    <v-divider></v-divider>
    <Contact></Contact>
  </div>
</template>

<script>
import About from "@/components/About";
import Contact from "@/components/Contact";
import Experience from "@/components/Experience";
import Projects from "@/components/Projects";
import Skills from "@/components/Skills";
export default {
  name: "Home",
  components: { About, Contact, Experience, Projects, Skills },
};
</script>
