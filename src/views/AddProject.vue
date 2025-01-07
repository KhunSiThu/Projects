<template>

<div class="flex items-center justify-center min-h-screen ">
  <form class="w-full max-w-lg">
    <h1 class="text-4xl font-extrabold text-center text-purple-600 mb-6">Add Project</h1>
    
    <div class="mb-5">
      <label for="title" class="block text-lg font-medium text-gray-700 mb-2">Project Title</label>
      <input 
        type="text" 
        id="title" 
        placeholder="Enter project title" 
        class="w-full border border-gray-300 rounded-lg focus:ring-purple-500 focus:border-purple-500 text-gray-700 p-3 shadow-sm"
      />
    </div>
    
    <div class="mb-5">
      <label for="detail" class="block text-lg font-medium text-gray-700 mb-2">Project Detail</label>
      <textarea 
        id="detail" 
        placeholder="Enter project details" 
        class="w-full border border-gray-300 rounded-lg focus:ring-purple-500 focus:border-purple-500 text-gray-700 p-3 shadow-sm resize-none"
        rows="4"
      ></textarea>
    </div>
    
    <button 
      type="submit" 
      class="w-full bg-gradient-to-r from-purple-500 to-purple-700 hover:from-purple-600 hover:to-purple-800 text-white font-semibold py-3 px-4 rounded-lg shadow-md transition duration-300 ease-in-out transform hover:scale-105"
    >
      Add Project
    </button>
  </form>
</div>




</template>

<script>
export default {

}
</script>

<style></style>