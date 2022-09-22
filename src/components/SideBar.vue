<template>
  <div class="px-5 pt-20">
    <nav>
      <ul class="flex flex-col gap-3 text-gray-500">
        <li
          v-for="({text, slug}, idx) in links" :key="idx">
          <a
            :href="`/${slug}`"
            @click.prevent="handleLinkClick(slug)"
            :class="`${current === slug ? 'text-blue-500' : ''}`"
          >icon {{ text }}</a>
        </li>
      </ul>
    </nav>
  </div>
</template>

<script>
export default {
  name: 'SideBar',
  data() {
    return {
      current: 'hot',
      links: [
        {
          text: '熱門報導',
          slug: 'hot',
        },
        {
          text: '台灣',
          slug: 'taiwan',
        },
        {
          text: '中國',
          slug: 'china',
        },
      ],
    };
  },
  methods: {
    handleLinkClick(slug) {
      this.current = slug;
      window.history.pushState(null, '', `/${slug}`);
    },
  },
};
</script>

<style scoped>

</style>
