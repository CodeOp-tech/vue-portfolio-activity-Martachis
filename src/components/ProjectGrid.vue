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
        <article class="grid-item" v-for="project in projects" :key="project.title">
            <img class="project-image" :src="project.image" :alt="project.title"/>
            <h2 class="project-title">{{ project.title }}</h2>
            <p class="project-description">{{ project.description }}</p>
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
    padding: 15px;
    align-items: start;
}

.empty-state{
    text-align: center;
    color: #9f5f05;
}

.title-empty-state{
    color: #4CAF50;
    font-size: 30px;
}

.project-title{
    max-width: 200px; 
    overflow: hidden;
    text-overflow: ellipsis;
    white-space: nowrap;
}
.project-image{
    aspect-ratio: 1;
    width: 100%;
    border-radius: 16px;
    object-fit: cover;
    max-height: 200px;
    max-width: 200px;
}

.project-description{
    display: flex;
    align-items: center;
    justify-content: center;
    margin-bottom: 30px;
    max-width: 200px; 
    overflow: hidden;
    text-overflow: ellipsis;
}
</style>
  