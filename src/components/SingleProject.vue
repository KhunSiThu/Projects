<template>
  <div  class="p-8 my-5 rounded bg-slate-100 border-l-4 border-red-500">
    <div class="flex justify-between items-center ">
      <h3 @click="showDetail = !showDetail" class="text-blue-500 text-xl font-bold cursor-pointer">{{ project.title }}</h3>
      <div class="flex justify-between items-center gap-5 text-gray-400">
        <button class= " hover:text-gray-600"><i class="fa-regular fa-circle-check"></i></button>
        <button class="hover:text-blue-600"><i class="fa-solid fa-pen-to-square"></i></button>
        <button class="hover:text-red-600"><i class="fa-solid fa-trash-can"></i></button>
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
    };
  },
};
</script>

<style></style>