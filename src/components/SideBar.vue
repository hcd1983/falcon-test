<template>
  <div class="px-5 pt-20">
    <nav>
      <ul class="flex flex-col gap-3 text-gray-500">
        <li
          v-for="(link, idx) in links" :key="idx">
          <a
            :href="`/${link.slug}`"
            @click.prevent="handleLinkClick(idx)"
            :class="`${current === idx ? 'text-blue-500' : ''}`"
          >icon {{ link.text }}</a>
        </li>
      </ul>
    </nav>
  </div>
</template>

<script>
export default {
  name: 'SideBar',
  props: ['links', 'current'],
  methods: {
    handleLinkClick(link) {
      this.$emit('linkClicked', link);
    },
  },
};
</script>

<style scoped>

</style>
