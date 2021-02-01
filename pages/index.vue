<template>
  <div class="">
    <Login v-if="!$auth.loggedIn"/>
    <div v-else>
      <h1 class=" px-3 text-4xl text-gray-700">
        Projects Board
      </h1>
      <div class="flex justify-between items-center px-3 pt-6">
        <h1 class="text-gray-700 text-sm font-normal">My Projects</h1>
        <button
          class="bg-blue-400 hover:bg-blue-400 uppercase text-xs text-white py-2 px-6 mr-6 rounded-full"
          @click.prevent="submit"
          >
            Create Project
          </button>
      </div>
      <div class="md:flex md:flex-wrap">
        <Project v-if="projects.length" v-for="project in projects" :key="project.id" :project="project"/>
        <div v-else>
          No projects yet.
        </div>
      </div>
    </div>
  </div>
</template>

<script type="text/javascript">
  export default {
    data () {
      return {
        projects: []
      }
    },
    async asyncData ({ app }) {
        if(app.$auth.loggedIn){
          console.log(app.$auth.loggedIn)
        let response = await app.$axios.$get('/projects')

        return {
          projects: response.data
        }
      }
    }
  }
</script>