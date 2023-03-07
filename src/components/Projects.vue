<script>
import axios from "axios";
import Card from "../components/CardProject.vue";

export default {
    data() {
        return {
             projects: [],
             projectsDesire: []
        }
    },
    components: {
        Card
    },
    async created() {
    let myGit = await axios.get(
      "https://api.github.com/users/Pedro-HenriqueDev"
    );
    let myrepos = await axios.get(myGit.data.repos_url);
    this.projects = myrepos.data;
    this.projectsDesire = myrepos.data;
  },
  methods: {
    desiredProjects(languageDesire) {
      let languages = languageDesire.split(" ");
      let projects = this.projects;
      console.log(languages);

      let projectsChoise = projects.filter((project) => {
        let equal = false;
        for (let lang of languages) {
          if (project.language == lang) {
            equal = true;
          }
        }
        if (equal) {
          return project;
        }
        return false;
      });

      return (this.projectsDesire = projectsChoise);
    },
    resetProjects() {
      this.projectsDesire = this.projects;
    },
  },
}
</script>

<template>
    <div class="m-10">
        <div id="projetos" class="ancora"></div>
        <h2 class="text-3xl text-color font-semibold" id="projetos">
          Projetos <span v-show="projectsDesire.length < 30" class="ml-3"><button @click="resetProjects" type="button"
            class="mr-10 -mx-1.5 -my-1.5 bg-white text-gray-400 hover:text-gray-900 rounded-lg focus:ring-2 focus:ring-gray-300 p-1.5 hover:bg-gray-100 inline-flex h-8 w-8 dark:text-gray-500 dark:hover:text-white dark:bg-gray-800 dark:hover:bg-gray-700"
            data-dismiss-target="#toast-default" aria-label="Close">
            <span class="sr-only">Close</span>
            <svg svg aria-hidden="true" class="w-5 h-5" fill="currentColor" viewBox="0 0 20 20"
              xmlns="http://www.w3.org/2000/svg">
              <path fill-rule="evenodd"
                d="M4.293 4.293a1 1 0 011.414 0L10 8.586l4.293-4.293a1 1 0 111.414 1.414L11.414 10l4.293 4.293a1 1 0 01-1.414 1.414L10 11.414l-4.293 4.293a1 1 0 01-1.414-1.414L8.586 10 4.293 5.707a1 1 0 010-1.414z"
                clip-rule="evenodd"></path>
            </svg>
          </button></span>
        </h2>
        <div class="w-full justify-center flex flex-wrap mt-8 gap-2">
          

          <button @click="desiredProjects('TypeScript')" type="button"
            class="text-white bg-blue-700 hover:bg-blue-800 font-medium rounded-full text-sm px-5 h-14 py-2.5 text-center mr-2 mb-2 dark:bg-blue-600 dark:hover:bg-blue-700 dark:focus:ring-blue-800">
            Typescript
          </button>

          <button @click="desiredProjects('Vue')" type="button"
            class="text-white bg-green-700 hover:bg-green-800 font-medium rounded-full text-sm px-5 h-14 py-2.5 text-center mr-2 mb-2 dark:bg-green-600 dark:hover:bg-green-700 dark:focus:ring-green-800">
            Vue
          </button>

          <button @click="desiredProjects('JavaScript')" type="button"
            class="text-white bg-yellow-400 hover:bg-yellow-500 font-medium rounded-full h-14 text-sm px-5 py-2.5 text-center mr-2 mb-2 dark:focus:ring-yellow-900">
            Javascript
          </button>

          <button @click="desiredProjects('HTML CSS SCSS')" type="button"
            class="text-white bg-purple-700 hover:bg-purple-800 font-medium rounded-full text-sm px-5 py-2.5 text-center mb-2 dark:bg-purple-600 dark:hover:bg-purple-700 dark:focus:ring-purple-900">
            HTML e CSS
          </button>
        </div>
        <div class="w-full mt-5 flex justify-center items-center gap-5 flex-wrap">
          <div class="flex justify-center items-center gap-5 flex-wrap" v-for="(project) in projectsDesire" :key="project.id">
            <Card :link="project.svn_url" :name="project.name" :language="project.language" />
          </div>
        </div>
      </div>
</template>


<style>
</style>