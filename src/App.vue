<template>
  <Layout v-if="data">
    <template #header>
      <Header />
    </template>
    <template #side>
      <SideBar :links="sideLinks" :current="currentLinkIdx" @linkClicked="linkClicked"/>
    </template>
    <template #main>
      <Content :title="contentTitle" :data="data" />
    </template>
    <template #footer>
      <Footer />
      <pre>{{ data }}</pre>
    </template>
  </Layout>
</template>

<script>
import axios from 'axios';
import Content from '@/components/Content.vue';
import Header from '@/components/Header.vue';
import Footer from '@/components/Footer.vue';
import SideBar from '@/components/SideBar.vue';
import Layout from '@/components/Layout.vue';
import testData from './develop_data/top-headlines.json';

const sideLinks = [
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
];
export default {
  name: 'App',
  components: {
    Header,
    Footer,
    SideBar,
    Content,
    Layout,
  },
  data() {
    return {
      // data: null,
      currentLinkIdx: 0,
      data: testData,
      sideLinks,
    };
  },
  mounted() {
    // this.getData();
  },
  computed: {
    contentTitle() {
      return this.sideLinks[this.currentLinkIdx].text;
    },
  },
  methods: {
    getData() {
      const url = 'https://newsapi.org/v2/top-headlines';
      const country = 'tw';
      const apiKey = 'c14ac1132c5b4fabac7ee0bb1818ea79';
      const options = {
        url,
        method: 'get',
        params: {
          country,
          apiKey,
        },
      };
      axios(options).then(({ data }) => {
        this.data = data;
      });
    },
    linkClicked(idx) {
      this.currentLinkIdx = idx;
      window.history.pushState(null, '', `/${this.sideLinks[idx].slug}`);
    },
  },
};
</script>
