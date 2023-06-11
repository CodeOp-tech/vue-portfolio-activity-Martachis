<template>
  <div>
    <h2>User View</h2>
    <project-grid :projects="projects" />
  </div>
</template>

<script>
import ProjectGrid from "./ProjectGrid.vue";

export default {
  name: "UserView",
  components: {
    projectGrid: ProjectGrid,
  },
  data (){
    return {
      projects: [],
    }
  },
};


</script>

<style></style>
