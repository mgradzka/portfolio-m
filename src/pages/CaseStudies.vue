<template>
  <main class="case">
    <case-teaser
      v-for="project in projects"
      :key="project.id"
      :id="project.id"
      :name="project.name"
      :role="project.role"
      :image="project.image"
      :tools="project.tools"
    ></case-teaser>
    <base-heading>Let's start working together!</base-heading>
    <base-container class="btn--container flex">
     
      <router-link to="/contact"
        ><base-button>Contact me</base-button></router-link
      
      >
    </base-container>
  </main>
</template>

<script>
import CaseTeaser from "../components/Case-studies/CaseTeaser.vue";
export default {
  data() {
    return {
      projects: [
        {
          name: "Task Portal",
          id: "case1",
          role: "Full Stack Developer",
          image: "taskportal.png",
          tools: "JavaScript, Node.js, MS SQL, CSS, HTMLL",
        },
        {
          name: "Kulia Foodtruck",
          id: "case2",
          role: "Frontend Developer, UX/UI designer",
          image: "kuliamobile.png",
          tools: "JavaScript, CSS, HTML",
        },
         {
          name: "Workout Noter",
          id: "case3",
          role: "Frontend Developer",
          image: "workout-design.png",
          tools: "Vue.js",
        },
      ],
    };
  },

  components: { CaseTeaser },
};
</script>

<style scoped>
.case > div {
  justify-content: center;
}

main {
  margin: 0 40rem 0;
}

@media (max-width: 1700px) {
 main {
  margin: 0 20rem 0;
}
}

@media (max-width: 1200px) {
 main {
  margin: 0;
}
}
</style>
