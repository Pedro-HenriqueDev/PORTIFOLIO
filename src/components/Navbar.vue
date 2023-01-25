<script>
export default {
  data() {
    return {
      offset: 0,
      navbarSm: false,
      navSm: false,
    };
  },
  created() {
    window.addEventListener("scroll", this.handleScroll);
    window.addEventListener("resize", this.navbarSmShow);
    this.navbarSmShow();
  },
  props: {
    hidden: Boolean,
  },
  methods: {
    handleScroll() {
      let offset = window.scrollY;
      this.offset = offset;
    },
    navbarSmShow() {
      if (window.innerWidth <= 640) {
        this.navbarSm = true;
        return;
      }
      this.navbarSm = false;
      return;
    },
    showSm() {
      this.navSm ? (this.navSm = false) : (this.navSm = true);
    },
  },
};
</script>

<template>
  <div class="w-full">
    <nav
      class="
        navbar
        mt-6
        -translate-y-6
        w-full
        flex
        justify-center
        items-center
        gap-10
        h-16
        text-slate-100
      "
      :class="[
        offset < 100 ? 'transparent' : 'shadow',
        !navbarSm ? 'flex' : 'hidden',
      ]"
    >
      <a href="#habilidades" class="cursor-pointer item-menu">Habilidades</a>
      <a href="#projetos" class="cursor-pointer item-menu">Projeto</a>
      <a href="#" class="cursor-pointer item-menu">Começo</a>
      <a href="#sobremim" class="cursor-pointer item-menu">Sobre mim</a>
      <a href="#objetivos" class="cursor-pointer item-menu">Objetivos</a>

      <div class="flex cursor-pointer gap-3 float-right">
        <a href="https://github.com/Pedro-HenriqueDev" target="_blank"><i class="block text-3xl devicon-github-original"></i></a>
        <a href="https://www.linkedin.com/in/pedro-henrique-6ab634229/" target="_blank"><i class="block text-3xl devicon-linkedin-plain"></i></a>
      </div>
    </nav>

      <div v-show="navbarSm" class="float-right" @click="showSm">
        <img class="w-10" src="../assets/img/menu.png" alt="" />
      </div>

      <div v-show="navbarSm">
        <Transition name="fade">
        <nav class="navbar-sm flex flex-col items-center pt-18" v-show="navSm">
          <div
            class="w-full h-14 flex justify-end items-center mr-5">
            <div class="w-full flex flex-col items-center text-center gap-8 mt-80 p-10">
              <div class="w-1/2">
                <a href="#habilidades" class="item-menu cursor-pointer">Habilidades</a>
              </div>
              <div class="w-1/2"><a href="#projetos" class="item-menu cursor-pointer">Projeto</a></div>
              <div class="w-1/2"><a href="#" class="item-menu cursor-pointer">Começo</a></div>
              <div class="w-1/2">
                <a href="#sobremim" class="item-menu cursor-pointer">Sobre mim</a>
              </div>
              <div class="w-1/2">
                <a href="#objetivos" class="item-menu cursor-pointer">Objetivos</a>
              </div>

              <div
                class="w-full h-auto justify-center flex cursor-pointer gap-3"
              >
                <a href="https://github.com/Pedro-HenriqueDev" target="_blank"><i class="block text-3xl devicon-github-original"></i></a>
                <a href="https://www.linkedin.com/in/pedro-henrique-6ab634229/" target="_blank"><i class="block text-3xl devicon-linkedin-plain"></i></a>
              </div>
            </div>
          </div>
        </nav>
    </Transition>
      </div>
  </div>
</template>

<style scoped>
.item-menu {
  width: auto;
  display: flex;
  flex-direction: column;
}
.item-menu::after {
  content: '';
  display: flex;
  justify-content: center;
  position: relative;
  width: 0%;
  height: 3px;
  border-radius: 5px;
  background: #fff;
  transition: all 250ms;
}
.item-menu:hover::after {
  content: '';
  width: 100%;
}

.fade-enter-active {
  transition: all 500ms ease-out;
}

.fade-leave-active {
  transition: all 500ms ease-in;
}

.fade-enter-from,
.fade-leave-to {
  transform: translateX(100px);
  opacity: 0;
}
.shadow {
  transition: all 500ms;
  background: rgba(0, 0, 0, 0.281);
}
.transparent {
  transition: all 500ms;
  background: transparent;
}
.navbar {
  animation: fade forwards alternate 500ms ease-in-out;
  position: fixed;
  width: 100%;
  color: #fffffe;
}
.navbar-sm {
  background: rgba(0, 0, 0, 0.281);
  position: fixed;
  right: 0;
  height: 100vh;
  width: 60%;
  color: #fffffe;
  z-index: 1;
}
.float-right {
  position: fixed;
  right: 0;
  padding: 15px 20px;
  z-index: 2;
}
</style>