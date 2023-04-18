<script>
import Navbar from "../components/Navbar.vue";
import Footer from "../components/Footer.vue";
import Skills from "../components/Skills.vue"
import AboutMe from "../components/AboutMe.vue"
import Projects from "../components/Projects.vue"
import Icons from "../components/Icons.vue"
import MainProjects from "../components/MainProjects.vue"

export default {
  data() {
    return {
      element: "",
      navbarShow: false
    };
  },
  components: {
    Navbar,
    Footer,
    Projects,
    Skills,
    AboutMe,
    Icons,
    MainProjects
  }
};
</script>

<template>
  <div class="conteudo">
    <div class="container-principal color-theme">
      <Navbar :hidden="navbarShow" />
      <div
        class="md:text-5xl lg:text-6xl md:flex-row md:justify-around text-5xl mx-5 flex flex-col items-center heightConteudo font-bold text-white">
        <div class="flex flex-col lg:mt-14 md:mt-20 mt-24">
          <div class="title -translate-x-6">
            Pedro Henrique
            <div class="animate-bounce subtitle text-right m-3 text-2xl">
              Web Developer Jr
            </div>
          </div>
          <div class="flex justify-center gap-4 mt-3 w-100 md:w-1/2 md:ml-7">
            <Icons linkIcon="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/nodejs/nodejs-original.svg" DelayMs="100" />
            <Icons linkIcon="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/nestjs/nestjs-plain.svg" DelayMs="200" />
            <Icons linkIcon="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/typescript/typescript-original.svg" DelayMs="300" />
            <Icons linkIcon="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/vuejs/vuejs-original.svg" DelayMs="400" />
            <Icons linkIcon="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/git/git-original.svg" DelayMs="500" />
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
      <AboutMe />
      <Skills />
      <MainProjects />
      <Projects />
    </div>
  </div>
  <Footer />
</template>

<style scoped>

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
  height: 100vh;
}

.color-theme {
  background: #232946;
}

.heightConteudo {
  height: 85%;
}

.card-custom {
  width: 300px;
}
@media (max-width: 576px) {
  .container-principal {
    height: 145vh;
  }
}
@media (min-width: 576px) {
  .container-principal {
    height: 115vh;
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

</style>
