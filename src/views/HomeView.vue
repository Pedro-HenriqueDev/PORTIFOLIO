<script>
import Navbar from "../components/Navbar.vue";
export default {
  data() {

    return {
      navbarShow: false
    }
  },
  components: {
    Navbar,
  }
};
</script>

<template>
  <div class="pb-80 conteudo">
    <div  class="container-principal">
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
        <div class="flex flex-col ml-10 mt-10">
          <div class="title -translate-x-6">
            Pedro Henrique
            <div class="animate-bounce subtitle text-right m-3 text-2xl">Web Developer Jr</div>
          </div>
          <div class="flex justify-center gap-4 mt-3 w-1/2">
              <img
              class="icons-animated translate-y-10 w-10"
              style="animation-delay: 100ms;"
              src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/nodejs/nodejs-original.svg"
            />
            
            <img
              class="icons-animated translate-y-10 w-10"
              style="animation-delay: 300ms;"
              src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/typescript/typescript-original.svg"
            />
            <img
              class="icons-animated translate-y-10 w-10"
              style="animation-delay: 500ms;"
              src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/vuejs/vuejs-original.svg"
            />
            <img
              class="icons-animated translate-y-10 w-10"
              style="animation-delay: 700ms;"
              src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/git/git-original.svg"
            />
          </div>
        </div>
        <div class="flex text-2xl">
          <div class=""><img class="md:w-96 w-80" src="../assets/img/bighead.svg"/></div>
        </div>
      </div>
    </div>
    <div class="main">
      <div class="m-10">
        <div id="sobremim" class="ancora"></div>
        <h2 class="text-3xl text-color font-semibold">Sobre mim</h2>
        <div class="mx-10 mt-5">
          Em 2021 consegui realizar alguns projetos com o básico conhecimento
          que eu tinha com HTML e CSS . Também realizei alguns cursos básicos na
          plataforma digital ,Digital Inovation One ,a qual estou me
          aprofundando em Desenvolvimento Web ,Back-end com a tecnologia Node.js
        </div>
      </div>
      <div class="m-10">
        <div id="objetivos" class="ancora"></div>
        <h2 class="text-3xl text-color font-semibold">Objetivos</h2>
        <div class="mx-10 mt-5">
          Em 2021 consegui realizar alguns projetos com o básico conhecimento
          que eu tinha com HTML e CSS . Também realizei alguns cursos básicos na
          plataforma digital ,Digital Inovation One ,a qual estou me
          aprofundando em Desenvolvimento Web ,Back-end com a tecnologia Node.js
        </div>
      </div>
      <div class="m-10">
        <div id="habilidades" class="ancora"></div>
        <h2 class="text-3xl text-color font-semibold">Habilidades</h2>
        <div class="mx-10 mt-5">
          Em 2021 consegui realizar alguns projetos com o básico conhecimento
          que eu tinha com HTML e CSS . Também realizei alguns cursos básicos na
          plataforma digital ,Digital Inovation One ,a qual estou me
          aprofundando em Desenvolvimento Web ,Back-end com a tecnologia Node.js
        </div>
      </div>
      <div class="m-10">
        <div id="projetos" class="ancora"></div>
        <h2 class="text-3xl text-color font-semibold" id="projetos">
          Projetos
        </h2>
        <div class="mx-10 mt-5">
          Em 2021 consegui realizar alguns projetos com o básico conhecimento
          que eu tinha com HTML e CSS . Também realizei alguns cursos básicos na
          plataforma digital ,Digital Inovation One ,a qual estou me
          aprofundando em Desenvolvimento Web ,Back-end com a tecnologia Node.js
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
.text-color {
  color: #121629;
}
.conteudo {
  background-color: #b8c1ec;
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
  background: #232946;

  border-bottom-right-radius: 10px;
  border-bottom-left-radius: 10px;
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
    transform: translateX(0)
  }
}
@keyframes transform {
  100% {
    opacity: 1;
    transform: translateY(0);
  }
}
</style>