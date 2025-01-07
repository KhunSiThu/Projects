<template>

    <nav class="flex justify-center items-center py-10">

        <!-- Navigation Links -->
        <div class="flex space-x-6">
            <router-link to="/" class="text-gray-700 font-bold  hover:text-purple-600 transition duration-300">
                Projects
            </router-link>
            <router-link :to="{ name: 'AddProject' }"
                class="text-gray-700 font-bold hover:text-purple-600 transition duration-300">
                Add Project
            </router-link>

        </div>
    </nav>


</template>

<script>
export default {

}
</script>

<style>
a.router-link-active {
    color: rgb(169, 44, 237);
}
</style>