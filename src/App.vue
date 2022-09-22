<template>
  <Header />
  <Content />
  <SideBar />
  <Footer />
</template>

<script>
import axios from 'axios';
import Content from '@/components/Content.vue';
import Header from '@/components/Header.vue';
import Footer from '@/components/Footer.vue';
import SideBar from '@/components/SideBar.vue';
import testData from './develop_data/top-headlines.json';

export default {
  name: 'App',
  components: {
    Header,
    Footer,
    SideBar,
    Content,
  },
  data() {
    return {
      // data: null,
      data: testData,
    };
  },
  mounted() {
    // this.getData();
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
  },
};
</script>
