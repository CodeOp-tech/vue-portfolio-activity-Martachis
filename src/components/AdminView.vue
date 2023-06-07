<template>
  <div>
    Title
    <input v-model="title" />
    <button @click="handleSubmit">SUBMIT</button>
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

<style>
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
  margin-left: 15px;
}
</style>
