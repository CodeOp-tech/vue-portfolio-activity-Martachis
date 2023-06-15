<template>
  <div>
    <h2>User View</h2>
    <project-detail-section v-if="selected !== null" :project="selected"/>
    <project-grid :projects="projects" @select="handleSelect"/>
  </div>
</template>

<script>
import ProjectGrid from "./ProjectGrid.vue";
import ProjectDetailSection from "./ProjectDetailSection.vue"

export default {
  name: "UserView",
  props: {
    projects: Array
  },
  components: {
    projectGrid: ProjectGrid,
    projectDetailSection: ProjectDetailSection,
  },
  data() {
    return {
      selected: null,
    };
  },
  methods: {
    handleSelect (project) {
      this.selected = project;
    }
  }
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
