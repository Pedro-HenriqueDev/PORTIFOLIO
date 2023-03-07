<script>

export default {
    props: {
        link: String,
        name: String,
        language: String
    }
}
</script>

<template>
    <div class="card-custom h-60">
              <a target="blank" :href="link"
                class="h-full block max-w-sm p-6 bg-white border border-gray-200 rounded-lg shadow hover:bg-gray-100 dark:bg-gray-800 dark:border-gray-700 dark:hover:bg-gray-700">
                <h5 class="break-words mb-2 text-2xl font-bold tracking-tight text-gray-900 dark:text-white">
                  {{ name }}
                  <p class="text-lg text-blue-400">
                    {{ language }}
                  </p>
                </h5>
              </a>
            </div>
</template>

<style scope>
.card-custom {
  width: 300px;
}
@media (min-width: 576px) {
  .card-custom {
    width: 380px;
  }
}

</style>