<script> 
  export default {
    name: "ProjectGrid",
    props: {
        projects: {
        type: Array,
        default: () => [],
        }
    }
  };

</script>
  
<template>
    <div v-if="projects.length > 0" class="grid">
        <article v-for="project in projects" :key="project.name">
            <h2>{{ project.name }}</h2>
            <image :src="project.image" :alt="project.name"/>
            <p>{{ project.description }}</p>
        </article>
    </div>
    <div class="empty-state" v-else>
        <h2 class="title-empty-state">Add a new project</h2>
        <p>And have fun!</p>
    </div>
</template>
  
  
  
<style scoped>
  
.grid{
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 35px;
    max-width: 1020px;
    width: 100%;
    margin: 0px;
    flex: 1;
}

.empty-state{
    text-align: center;
    color: #9f5f05;
}

.title-empty-state{
    color: #4CAF50;
    font-size: 30px;
}
</style>
  