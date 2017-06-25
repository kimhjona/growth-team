


<template>
  <div class='content'>
    <p class='contentText'>Search Gems</p>
    <p>
      <input class='inputBar' placeholder='Search' v-model='input'>
      </input>
      <img class='magnifying-glass' width='17' src='./../assets/magnifying-glass.png' @click='apisearch'>
    </p>
    <p v-if='data'>
      {{ data }}
    </p>
  </div>
</template>

<script>
import Vue from 'vue';
import axios from 'axios';
import VueAxios from 'vue-axios';

Vue.use(VueAxios, axios);
// Vue.http.options.emulateJSON = true;
// Vue.http.headers.common['Access-Control-Allow-Origin'] = 'http://xxx.xxx.xxx.xxx:94';
// Vue.http.headers.common['Access-Control-Request-Method'] = '*';

export default {
  name: 'Search',
  data() {
    return {
      input: '',
      data: [],
      errorMsg: '',
    };
  },
  methods: {
    apisearch() {
      const apiKey = {
        headers: {
          'Access-Control-Allow-Origin': '*',
          Authorization: 'ba903262ee1bde9f19de510f4b66ddf7',
        },
      };
      const api = `https://rubygems.org/api/v1/${this.input}.json`;
      Vue.axios.get(api, apiKey).then((resp) => {
        console.log('resp:', resp);
        this.data = resp;
      }).catch((error) => {
        this.errorMsg = 'Something went wrong!';
        console.log(error);
        this.data = [];
      });
    },
  },
};
</script>

<style>
  .magnifying-glass {
    position: absolute;
    left: 445px;
    top: 120px;
    cursor: pointer;
  }

</style>
