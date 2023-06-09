<template>
  <div id="principal-content">
    <h1>My Portfolio</h1>
    <div class="button-container">
      <button @click="isAdmin = true" :class="{ 'color-admin-button': isAdmin === true}">ADMIN</button>
      <button @click="isAdmin = false" :class="{ 'color-user-button': isAdmin === false}">USER</button>
    </div>
    <admin-view v-if="isAdmin" @createProject="addProject" />
    <user-view v-else />

  </div>
</template>


<script>
import AdminView from "./components/AdminView.vue";
import UserView from "./components/UserView.vue";

export default {
  name: "app",
  components: {
    userView: UserView,
    adminView: AdminView
  },
  data() {
    return {
      isAdmin: true,
      allProjects: []
    };
  },
  methods: {
    addProject(project) {
      this.allProjects.push(project);
    }
  }
};
</script>

<style scoped>
  .color-user-button, 
.color-admin-button{
    background-color: #4CAF50;
    border-radius: 5px;
    color: white;
    padding: 15px 32px;
    text-align: center;
    text-decoration: none;
    display: inline-block;
    font-size: 16px;
    
  }
  
  .color-admin-button {
    border: none;
  }

  button {
    margin: 10px;
    margin-bottom: 30px;
    border: none;
    background-color: #BFC9BC;
    padding: 2px 32px;
    border-radius: 5px;
    font-family: 'Lucida Sans';
  }
  
  h1 {
    font-family: 'Lucida Sans';
    color: #4CAF50;
  }

  #principal-content{
    display: flex;
    flex-direction: column;
    align-items: center;
    height: 100vh;
    font-family: 'Lucida Sans';
  }

  .button-container {
    display: flex;
    justify-content: center;
    margin-bottom: 40px; 
  }
  
  .button-container button {
    margin: 0 10px; 
  }
</style>
