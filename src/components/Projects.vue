<script>
import axios from "axios";
import Card from "../components/CardProject.vue";

export default {
    data() {
        return {
            projects: [],
            projectsDesire: [],
            numberOfProjects: 0
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
    this.numberOfProjects = myrepos.data.length
  },
  methods: {
    desiredProjects(languageDesire) {
      let languages = languageDesire.split(" ");
      let projects = this.projects;

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
      this.numberOfProjects = this.projects.length
    },
  },
}
</script>

<template>
    <div class="w-100 theme">
        <div id="projetos" class="ancora"></div>
        <div class="p-10">
            <h2 class="text-3xl text-color font-semibold" id="projetos">
            Projetos 
            </h2>
            <div class="w-full justify-center flex flex-wrap mt-8 gap-2">
              <div class="flex border-r-2 border-rounded border-gray-400">
                <button @click="projectsDesire = projects" type="button" class=" border border-gray-300 text-white bg-gray-800 hover:bg-gray-900 font-medium rounded-full text-sm px-5 py-2.5 mr-5 mb-2">Todos</button>
              </div>
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
      </div>
</template>


<style scoped>
.theme {
    color: #fffffe;
    background-color: #232946;
}
</style>