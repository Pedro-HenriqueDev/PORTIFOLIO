<script>
import Navbar from "../components/Navbar.vue";
import axios from 'axios'
export default {
  data() {
    return {
      element: "",
      navbarShow: false,
      projects: []
    }
  },
  async created() {
    let myGit = await axios.get("https://api.github.com/users/Pedro-HenriqueDev")
    let myrepos = await axios.get(myGit.data.repos_url)
    this.projects = myrepos.data
  },
  components: {
    Navbar,
  },
  methods: {},
};
</script>

<template>
  <div class="pb-80 conteudo">
    <div class="container-principal color-theme">
      <Navbar :hidden="navbarShow" />
      <div
        class="
          md:text-7xl
          lg:flex-row lg:justify-around
          text-5xl
          mx-5
          flex flex-col
          items-center
          heightConteudo
          font-bold
          text-white
        "
      >
        <div class="flex flex-col ml-10 lg:mt-14 md:mt-20 mt-20">
          <div class="title -translate-x-6">
            Pedro Henrique
            <div class="animate-bounce subtitle text-right m-3 text-2xl">
              Web Developer Jr
            </div>
          </div>
          <div class="node flex justify-center gap-4 mt-3 w-1/2">
            <img
              class="icons-animated translate-y-10 w-10"
              style="animation-delay: 100ms"
              src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/nodejs/nodejs-original.svg"
            />

            <img
              class="icons-animated translate-y-10 w-10"
              style="animation-delay: 300ms"
              src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/typescript/typescript-original.svg"
            />
            <img
              class="icons-animated translate-y-10 w-10"
              style="animation-delay: 500ms"
              src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/vuejs/vuejs-original.svg"
            />
            <img
              class="icons-animated translate-y-10 w-10"
              style="animation-delay: 700ms"
              src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/git/git-original.svg"
            />
          </div>
        </div>
        <div class="flex text-2xl">
          <div class="">
            <img class="md:w-96 w-80" src="../assets/img/bighead.svg" />
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
            <p>Tenho atualmente 18 anos e estudo programaçao a 1 ano e 6 meses.
            Moro na Bahia e estou cursando Analise e Desenvolvimento de
            Sistemas. Tenho muito apreço pela tecnologia e pela forma que ela resolve os problemas do nosso dia-a-dia.</p> <br>
            <p>Me profissionalizo hoje
            no Desenvolvimento Web com tecnologias altamente usadas no mercado,
            como Node.js e Typescript.</p> 
          </div>
        </div>
        <div class="md:w-1/2 mt-10 md:m-10 w-full">
          <div id="objetivos" class="ancora"></div>
          <h2 class="text-3xl text-color font-semibold">Objetivos</h2>
          <div class="lg:mx-10 mt-5">
            <ul class="list-disc">
              <li>
                Tenho como Objetivo o Desenvolvedor FullStack, desenvolvendo
                aplicaçoes Web front-end, back-end e tambem Mobile.
              </li>
              <li>
                Meu principal Objetivo hoje er me aperfeiçoar no desenvolvimento Back-end com
                Node.js.
              </li>
              <li>
                Desejo tambem entrar no mercado de trabalho e promover o
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
              <li>Boa Logica de Programaçao</li>
              <li>Autodisciplina</li>
              <li>Aprendizado contínuo</li>
              <li>Adaptabilidade</li>
            </ul>
          </div>

          <div>
            <h3 class="lg:mt-0 mt-10 text-xl">Tecnologias Back-end</h3>
            <ul class="gap-3 mt-5 flex justify-center text-sm">
              <li>
                <img
                  class="w-10"
                  src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/nodejs/nodejs-original.svg"
                />
              </li>
              <li>
                <img
                  class="w-10"
                  src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/typescript/typescript-original.svg"
                />
              </li>
              <li>
                
            <img class="w-10" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/mysql/mysql-original.svg" />
          
              </li>
              <li>
                
            <img class="w-10" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/postgresql/postgresql-original.svg" />
          
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
                <img
                  class="w-10"
                  src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/html5/html5-original.svg"
                />
              </li>
              <li>
                <img
                  class="w-10"
                  src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/css3/css3-original.svg"
                />
              </li>
              <li>
                <img
                  class="w-10"
                  src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg"
                />
              </li>
              <li>
                <img
                  class="w-10"
                  src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/vuejs/vuejs-original.svg"
                />
              </li>
              <li>
                <img
                  class="w-10"
                  src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/tailwindcss/tailwindcss-plain.svg"
                />
              </li>
            </ul>
          </div>
        </div>
      </div>
      <div class="m-10">
        <div id="projetos" class="ancora"></div>
        <h2 class="text-3xl text-color font-semibold" id="projetos">
          Projetos
        </h2>
        <p class="text-red-500">EM CONSTRUÇAO</p>
        <div class="mx-10 w-full mt-5 flex gap-5 flex-wrap">
          
          <div v-for="project in projects" :key="project.id">
            <div class="w-96 h-60">
              <router-link target="blank"
            :to="project.url"
            class="
              h-full w-96
              block
              max-w-sm
              p-6
              bg-white
              border border-gray-200
              rounded-lg
              shadow
              hover:bg-gray-100
              dark:bg-gray-800 dark:border-gray-700 dark:hover:bg-gray-700
            "
          >
            <h5
              class="
                mb-2
                text-2xl
                font-bold
                tracking-tight
                text-gray-900
                dark:text-white
              "
            >
              {{ project.name }}
              <p class="text-lg text-blue-400">
                {{ project.language }}
              </p>
            </h5>
            <p class="font-normal text-gray-700 dark:text-gray-400">
              {{project.description}}
            </p>
          </router-link>
        </div>
          </div>          
        </div>
      </div>
    </div>
  </div>
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
  height: 110vh;
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