<template>
<div class="px-10 py-10">
  <div class="flex justify-between">
    <h2 class="text-xl">{{ title }}</h2>
    <div class="text-gray-500">由 Microsoft 支援</div>
  </div>
  <div>
    <div class="grid grid-cols-3 gap-5">

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
