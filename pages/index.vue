<template>
  <div class="mx-auto">
    <Login v-if="!$auth.loggedIn"/>
    <div v-else>
      <h1 class=" ml-5 text-4xl text-gray-700">
        Project Board
      </h1>
      <Project v-for="project in projects" :key="project.id" :project="project"/>
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
        let response = await app.$axios.$get('/projects')

        return {
          projects: response.data
        }
      }
    }
  }
</script>