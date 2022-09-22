<template>
<div class="px-10 py-10">
  <div class="flex justify-between">
    <h2 class="text-xl">{{ title }}</h2>
    <div class="text-gray-500">由 Microsoft 支援</div>
  </div>
  <div class="mt-8">
    <div class="grid grid-cols-3 gap-5 max-w-[990px]">
      <section v-for="({title, url, urlToImage, author, publishedAt}, idx) in articles" :key="idx" class="rounded-lg overflow-hidden pb-3 border border-gray-300">
        <a :href="url">
          <img :src="urlToImage" :alt="title" class="w-full h-[200px] object-cover"/>
        </a>
        <div class="px-5">
          <a :href="url">
            <h2 class="texl-xl font-bold mt-3 h-20">{{ title }}</h2>
          </a>
          <div class="flex justify-between items-baseline">
            <h4 class="mt-5">{{ author }}</h4>
            <time class="text-right">{{ publishedAt }}</time>
          </div>
        </div>
      </section>
    </div>
  </div>
</div>
</template>

<script>
export default {
  name: 'MyContent',
  props: ['title', 'data'],
  computed: {
    articles() {
      return this.data.articles;
    },
  },
};
</script>

<style scoped>

</style>
