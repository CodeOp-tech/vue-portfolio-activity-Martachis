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
  props: {
    projects: Array
  },
  components: {
    projectGrid: ProjectGrid,
  },
};


</script>

<style>

h2{
  font-family: monospace;
  display: flex;
  align-items: center;
  justify-content: center;
  color: #F9BB62;
  margin-bottom: 30px;
  font-size: 30px;
}

</style>
