<template>
  <div class="p-8 my-5 rounded bg-slate-100 border-l-4 border-red-500" :class="{'border-green-500':project.complete}">
    <div class="flex justify-between items-center ">
      <h3 @click="showDetail = !showDetail" class="text-blue-500 text-xl font-bold cursor-pointer">{{ project.title }}
      </h3>
      <div class="flex justify-between items-center gap-5 text-gray-400">
        <button @click="completeProject" class=" text-red-500"><i class="fa-regular fa-circle-check " :class="{'text-green-500':project.complete}" ></i></button>
        <button class="hover:text-blue-600"><i class="fa-solid fa-pen-to-square"></i></button>
        <button @click="deleteProject" class="hover:text-red-600"><i class="fa-solid fa-trash-can"></i></button>
      </div>
    </div>
    <p v-if="showDetail" class="text-slate-600 mt-3">{{ project.detail }}</p>
  </div>
</template>

<script>


export default {
  props: ["project"],

  data() {
    return {
      showDetail: false,
      api: 'http://localhost:3000/projects/',
    };
  },

  methods: {
    deleteProject() {

      let deleteRoute = this.api+this.project.id;

      fetch(deleteRoute, { method: "DELETE" })
      .then(()=>{
        this.$emit("delete",this.project.id);
      })

    },

    completeProject(){
      let updateCompleteRoute = this.api+this.project.id;
      fetch(updateCompleteRoute,{
        method:'PATCH',
        headers:{
          "Content-Type":"application/json"
        },
        body:JSON.stringify({
          complete:!this.project.complete
        })
      })
      .then(()=>{
        this.$emit("complete",this.project.id);
      })
      .catch(()=>{console.log(err)});
    }
  }
};
</script>

<style></style>