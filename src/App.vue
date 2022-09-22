<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome to Your Vue.js App"/>
  <h1 class="text-blue-700">Hello</h1>
  <pre>{{ data }}</pre>
</template>

<script>
import axios from 'axios';
import HelloWorld from './components/HelloWorld.vue';

export default {
  name: 'App',
  components: {
    HelloWorld,
  },
  data() {
    return {
      data: null,
    };
  },
  mounted() {
    this.getData();
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

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
