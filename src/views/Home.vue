<template>
  <v-container fluid fill-height>
    <h1 class="pb-5">Discovery</h1>
    <v-skeleton-loader
        class="mx-auto"
        type="card"
        width="100%"
        v-if="!loaded"
    ></v-skeleton-loader>

    <div style="width: 100%">
      <Tweet @done="newTweet"/>
    </div>

  

  </v-container>
</template>

<script>

import api from "../services/api"

import Tweet from "../components/Tweet"
import cookies from "vue-cookies"

export default {
  components:{
    
    Tweet,
  
    },

  name: 'Home',

  data() {
    return {
      loaded:false,
      tweets:[],
      authUser: cookies.get('userId')
    }
  },

}
</script>
<style scoped>
  h1 {
    padding-bottom: 20px;
  }
</style>