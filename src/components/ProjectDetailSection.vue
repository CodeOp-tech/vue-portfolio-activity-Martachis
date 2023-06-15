<script> 
  export default {
    name: "ProjectDetailSection",
    props: ["project"]
  };

</script>
  
<template>
    <section class="detail-section">
        <img class="detail-section-img" :src="project.image"
        :alt="project.title"/>

        <div class="detail-information">
            <h2 class="detail-information-title">{{project.title}}</h2>
            <p class="detail-information-description">Description: {{project.description}}</p>
        </div>
    </section>
</template>
  
  
  
<style scoped>

.detail-section{
  display: flex;
  gap: 32px;
  background-color: rgb(179, 215, 204);
  padding-left: 80px;
  padding-right: 80px;
  padding-top: 15px;
  padding-bottom: 15px;
  border-radius: 15px;
  box-shadow: rgba(255, 255, 255, 0.1) 0px 1px 1px 0px inset, rgba(50, 50, 93, 0.25) 0px 50px 100px -20px, rgba(0, 0, 0, 0.3) 0px 30px 60px -30px;
  margin-bottom: 40px;
}

.detail-section-img {
  aspect-ratio: 1;
  width: 250px;
  border-radius: 50%;
  object-fit: cover;
  box-shadow: rgba(255, 255, 255, 0.1) 0px 1px 1px 0px inset, rgba(50, 50, 93, 0.25) 0px 50px 100px -20px, rgba(0, 0, 0, 0.3) 0px 30px 60px -30px;
}

.detail-information {
  display: flex;
  flex-direction: column;
  gap: 8px;
}

.detail-information-title{
  font-size: 28px;
  margin: 0;
  color: #275a29;
}

.detail-information-description {
  font-size: 15px;
  margin: 0;
  margin-top: 10px;
}

</style>
  