<script>
import Navbar from "../components/Navbar.vue";
import Footer from "../components/Footer.vue";

import axios from "axios";

export default {
  data() {
    return {
      element: "",
      navbarShow: false,
      projects: [],
      projectsDesire: [],
    };
  },
  async created() {
    let myGit = await axios.get(
      "https://api.github.com/users/Pedro-HenriqueDev"
    );
    let myrepos = await axios.get(myGit.data.repos_url);
    this.projects = myrepos.data;
    this.projectsDesire = myrepos.data;
  },
  components: {
    Navbar,
    Footer,
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
};
</script>

<template>
  <div class="pb-20 conteudo">
    <div class="container-principal color-theme">
      <Navbar :hidden="navbarShow" />
      <div
        class="md:text-6xl lg:text-7xl lg:flex-row lg:justify-around text-5xl mx-5 flex flex-col items-center heightConteudo font-bold text-white">
        <div class="flex flex-col ml-10 lg:mt-14 md:mt-20 mt-24">
          <div class="title -translate-x-6">
            Pedro Henrique
            <div class="animate-bounce subtitle text-right m-3 text-2xl">
              Web Developer Jr
            </div>
          </div>
          <div class="node flex justify-center gap-4 mt-3 w-1/2">
            <img class="icons-animated translate-y-10 w-10" style="animation-delay: 100ms"
              src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/nodejs/nodejs-original.svg" />

            <img class="icons-animated translate-y-10 w-10" style="animation-delay: 300ms"
              src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/typescript/typescript-original.svg" />
            <img class="icons-animated translate-y-10 w-10" style="animation-delay: 500ms"
              src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/vuejs/vuejs-original.svg" />
            <img class="icons-animated translate-y-10 w-10" style="animation-delay: 700ms"
              src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/git/git-original.svg" />
          </div>
          <div class="w-full mt-10">
            <a target="_blanck" href="https://github.com/Pedro-HenriqueDev">
              <button type="button"
                class="text-white bg-[#1e2227] hover:bg-[#24292F]/90 font-medium rounded-lg text-sm px-5 py-2.5 text-center inline-flex items-center dark:focus:ring-gray-500 dark:hover:bg-[#050708]/30 mr-5 mb-2">
                <i class="block mr-2 text-lg devicon-github-original"></i>
                Siga-me no Github
              </button>
            </a>
            <a target="_blanck" href="https://www.linkedin.com/in/pedro-henrique-6ab634229/">
              <button type="button"
                class="text-white bg-[#4285F4] hover:bg-[#4285F4]/90 font-medium rounded-lg text-sm px-5 py-2.5 text-center inline-flex items-center mr-2 mb-2">
                <i class="block mr-2 text-lg devicon-linkedin-plain"></i>
                Siga-me no Linkedin
              </button>
            </a>
          </div>
        </div>
        <div class="flex text-2xl">
          <div class="">
            <img class="lg:w-96 md:w-80 w-64 rounded-full" src="../assets/img/8750fc89-cb12-4cd2-bc23-1db6ec6cdbb8.jpeg" />
          </div>
        </div>
      </div>
    </div>
    <div class="main">
      <div class="flex flex-col md:flex-row p-8 md:p-12">
        <div class="md:m-10 md:w-1/2 w-full">
          <div id="sobremim" class="ancora"></div>
          <h2 class="text-3xl text-color font-semibold">Sobre mim</h2>
          <div class="lg:mx-10 mt-5">
            <p>
              Tenho atualmente 18 anos e estudo programação a 1 ano e 6 meses.
              Moro na Bahia e estou cursando Analise e Desenvolvimento de
              Sistemas. Tenho muito apreço pela tecnologia e pela forma que ela
              resolve os problemas do nosso dia-a-dia.
            </p>
            <br />
            <p>
              Me profissionalizo hoje no Desenvolvimento Web com tecnologias
              altamente usadas no mercado, como Node.js e Typescript.
            </p>
          </div>
        </div>
        <div class="md:w-1/2 mt-10 md:m-10 w-full">
          <div id="objetivos" class="ancora"></div>
          <h2 class="text-3xl text-color font-semibold">Objetivos</h2>
          <div class="lg:mx-10 mt-5">
            <ul class="list-disc">
              <li>
                Tenho como Objetivo o Desenvolvedor FullStack, desenvolvendo
                aplicações Web front-end, back-end e também Mobile.
              </li>
              <li>
                Meu principal Objetivo hoje é me aperfeiçoar no desenvolvimento
                Back-end com Node.js.
              </li>
              <li>
                Desejo também entrar no mercado de trabalho e promover o
                crescimento mutuo entre mim e a empresa
              </li>
            </ul>
          </div>
        </div>
      </div>
      <div class="px-10 py-20 color-theme">
        <div id="habilidades" class="ancora"></div>
        <h2 class="text-3xl text-gray-100 font-semibold">Habilidades</h2>
        <div class="text-gray-100 lg:flex-row flex-col flex lg:items-start items-center justify-around mx-10 mt-10">
          <div>
            <h3 class="text-xl">Habilidades Profissionais</h3>
            <ul class="mt-5 gap-3 flex flex-col items-center text-sm">
              <li>Boa lógica de programação</li>
              <li>Autodisciplina</li>
              <li>Aprendizado contínuo</li>
              <li>Adaptabilidade</li>
            </ul>
          </div>

          <div>
            <h3 class="lg:mt-0 mt-10 text-xl">Tecnologias Back-end</h3>
            <ul class="gap-3 mt-5 flex justify-center text-sm">
              <li>
                <img class="w-10" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/nodejs/nodejs-original.svg" />
              </li>
              <li>
                <img class="w-10"
                  src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/typescript/typescript-original.svg" />
              </li>
              <li>
                <img class="w-10" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/mysql/mysql-original.svg" />
              </li>
              <li>
                <img class="w-10"
                  src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/postgresql/postgresql-original.svg" />
              </li>
              <li>
                <img class="w-10" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/jest/jest-plain.svg" />
              </li>
            </ul>
          </div>

          <div>
            <h3 class="lg:mt-0 mt-10 text-xl">Tecnologias Front-end</h3>
            <ul class="gap-3 mt-5 flex items-center text-sm">
              <li>
                <img class="w-10" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/html5/html5-original.svg" />
              </li>
              <li>
                <img class="w-10" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/css3/css3-original.svg" />
              </li>
              <li>
                <img class="w-10"
                  src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg" />
              </li>
              <li>
                <img class="w-10" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/vuejs/vuejs-original.svg" />
              </li>
              <li>
                <img class="w-10"
                  src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/tailwindcss/tailwindcss-plain.svg" />
              </li>
            </ul>
          </div>
        </div>
      </div>
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
            <div class="card-custom h-60">
              <a target="blank" :href="project.svn_url"
                class="h-full block max-w-sm p-6 bg-white border border-gray-200 rounded-lg shadow hover:bg-gray-100 dark:bg-gray-800 dark:border-gray-700 dark:hover:bg-gray-700">
                <h5 class="break-words mb-2 text-2xl font-bold tracking-tight text-gray-900 dark:text-white">
                  {{ project.name }}
                  <p class="text-lg text-blue-400">
                    {{ project.language }}
                  </p>
                </h5>
                <p class="font-normal text-gray-700 dark:text-gray-400">
                  {{ project.description }}
                </p>
              </a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
  <Footer />
</template>

<style scoped>
.icons-animated {
  opacity: 0;
  animation: transform forwards alternate 500ms ease-in-out;
}

.conteudo {
  background: #d4d8f0;
}

.text-color {
  color: #121629;
}

.title {
  animation: fade forwards alternate 500ms ease-in-out;
  color: #fffffe;
}

.subtitle {
  color: #b8c1ec;
}

.container-principal {
  width: 100%;
  height: 115vh;
}

.color-theme {
  background: #232946;
}

.ancora {
  position: absolute;
  width: 1px;
  height: 1px;
  left: 0;
  margin-top: -100px;
  background-color: transparent;
  z-index: -1;
}

.heightConteudo {
  height: 85%;
}

.card-custom {
  width: 300px;
}
@media (min-width: 768px) {
  .card-custom {
    width: 380px;
  }
}

@keyframes fade {
  0% {
    opacity: 0;
  }

  100% {
    opacity: 1;
    transform: translateX(0);
  }
}

@keyframes transform {
  100% {
    opacity: 1;
    transform: translateY(0);
  }
}
</style>
