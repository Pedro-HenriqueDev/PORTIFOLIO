<script>
import axios from "axios";

export default {
    data() {
        return {
            projects: [],
        };
    },
    async created() {
        const projects = await axios.get("./projects.json");
        this.projects = projects.data;
    },
    methods: {
        next() { },
    },
};
</script>

<template>
    <h2 class="text-3xl text-color font-semibold m-10 md:m-10 md:w-1/2">
        Destaques
    </h2>
    <div class="w-100 m-10 pb-10">
        <div class="gap-4">
            <div class="flex justify-center flex-wrap items-center gap-4">
                    <div v-for="project in projects" :key="project.id"
                        class="max-w-sm bg-white border border-gray-200 rounded-lg shadow dark:bg-gray-800 w-72 h-80 mt-5">
                        <div v-if="project.image_url == ''">
                            <div class="rounded-t-lg w-100 h-36 flex items-center justify-center"> 
                                <div class="text-white">
                                    Projeto Back-end!
                                </div>
                            </div>
                        </div>
                        <div class="h-36" v-else>
                            <img class="rounded-t-lg w-full " :src="project.image_url" alt="" />
                        </div>
                        
                        <div class="p-5 h-36">
                            <h5 class="mb-2 text-2xl font-bold tracking-tight text-gray-900 dark:text-white">
                                {{ project.name }}
                            </h5>
                            <p class="mb-3 font-normal text-gray-700 dark:text-gray-400">
                                {{ project.description }}
                            </p>
                        </div>
                        <div class="bottom-0 left-0 z-50 w-full h-16 rounded-b-lg bg-white border-t border-gray-200 dark:bg-gray-700 dark:border-gray-600">
                            <div class="grid h-full max-w-lg grid-cols-2 mx-auto ">
                                <a :href="project.link" target="blank_" type="button" class="rounded-b-lg inline-flex flex-col items-center justify-center font-medium px-5 hover:bg-gray-50 dark:hover:bg-gray-800 group">
                                    <span class="text-2xl text-gray-400"><i class="devicon-chrome-plain"></i></span>
                                </a>
                                <a :href="project.repo" target="blank_" type="button" class="rounded-b-lg inline-flex flex-col items-center justify-center font-medium px-5 hover:bg-gray-50 dark:hover:bg-gray-800 group">
                                    <span class="text-2xl text-gray-400"><i class="devicon-github-original"></i></span>
                                </a>
                            </div>
                        </div>
                    </div>
                
            </div>
        </div>
    </div>
</template>

<style scoped>
.div-mainProjects {
    width: 100%;
}

.container-projects {
    width: 90%;
    display: flex;
    overflow: auto;
    gap: 15px;
}

.carrousel-custom {
    display: flex;
    justify-content: center;
}

.carrousel-custom>div {
    width: 80%;
    height: 600px;
    display: flex;
    justify-content: center;
}
</style>
