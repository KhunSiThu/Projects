<template>
  <div class="home">
    <h1 class="text-4xl font-extrabold  text-purple-600 mb-10">Projects</h1>
    <div v-for="project in projects" :key="project.id">
      <SingleProject :project="project" @delete="deleteProject" @complete="completeProject"></SingleProject>
    </div>
  </div>
</template>

<script>




import SingleProject from '../components/SingleProject'
export default {
  name: 'HomeView',
  components: {
    SingleProject,

  },


  data() {
    return {
      projects: [],
    }
  },

  methods: {
    deleteProject(id) {
      this.projects = this.projects.filter((pro) => pro.id != id)
    },

    completeProject(id) {
      // this.projects = this.projects.map((pro) => {
      //   if (pro.id === id) {
      //     return { ...pro, complete: !pro.complete }; 
      //   }
      //   return pro; 
      // });

      let findProject = this.projects.find(pro => {
        return pro.id === id;
      });

      findProject.complete = !findProject.complete;
    }

  },

  mounted() {
    fetch("http://localhost:3000/projects")
      .then((response) => {
        return response.json();
      })
      .then((datas) => {
        this.projects = datas;
      })
      .catch(() => {

      })
  },
}
</script>
