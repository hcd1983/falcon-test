<template>
  <div class="px-3 py-4 flex justify-between text-gray-500">
    <nav>
      <ul class="flex gap-3">
        <li v-for="({link, text}, idx) in links" :key="idx">
          <a :href="link">{{ text }}</a>
        </li>
      </ul>
    </nav>
    <div>@2121 Microsoft</div>
  </div>
</template>

<script>
export default {
  name: 'MyFooter',
  data() {
    return {
      links: [
        {
          text: '隱私權和 Cookie',
          link: 'javascript:void(0)',
        },
        {
          text: '法律聲明',
          link: 'javascript:void(0)',
        },
        {
          text: '廣告',
          link: 'javascript:void(0)',
        },
        {
          text: '我們的廣告',
          link: 'javascript:void(0)',
        },
        {
          text: '說明',
          link: 'javascript:void(0)',
        },
        {
          text: '意見反應',
          link: 'javascript:void(0)',
        },
      ],
    };
  },
};
</script>

<style scoped>

</style>
