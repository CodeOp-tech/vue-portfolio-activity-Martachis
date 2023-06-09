<template>
  <div>
    <h2>CREATE NEW PROJECT</h2>
    <form>
        <div class="title-url-fields">

          <div class="text-field">
            <label htmlForm="project-title">Project title</label>
            <input id="project-title" type="text" name="project-title" v-model="title" />
          </div>

          <div class="text-field">
            <label htmlForm="project-url">Image URL</label>
            <input id="project-url" type="url" name="project-url" v-model="image" />
          </div>

        </div>
        <div class="text-field">
            <label htmlForm="project-decription">Project Description</label>
            <input id="project-decription" type="text" name="project-decription" v-model="description" />
        </div>
        <div class="button-cointainer">
          <button type="submit" @click="handleSubmit">SUBMIT</button>
        </div>
    </form>
  </div>
</template>

<script>



export default {
  name: "AdminView",
  data() {
    return {
      title: "",
      image: "",
      description: ""
    };
  },
  methods: {
    handleSubmit() {
      this.$emit("createProject", {
        title: this.title,
        image: this.image,
        description: this.description
      });      
    }
  }
};
</script>



<style scoped>

.button-cointainer{
  justify-content: center;
  display: flex;
}

button {
  background-color: #F9BB62;
  border-radius: 5px;
  color: white;
  padding: 3px 12px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  border: none;
  display: flex;
  margin-top: 30px;
  cursor: pointer;
}

button:hover{
  background-color: #eed8bc;
}

button:active{
  background-color: #9f5f05;
}

h2{
  font-family: monospace;
  display: flex;
  align-items: center;
  justify-content: center;
  color: #F9BB62;
  margin-bottom: 30px;
}

.text-field{
  display: flex;
  flex-direction: column;
  gap: 8px;
  font-family: 'Lucida Sans';
}
.title-url-fields {
  display: flex;
  margin-bottom: 40px;
  gap: 20px;
}

#project-decription{
  height: 80px;
}

input {
  border: none;
  background-color: rgb(250, 228, 196);
  border-radius: 8px;
  padding-top: 10px;
}

</style>
