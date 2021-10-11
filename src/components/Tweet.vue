<template>
  <v-card
      class="mt-4"
      elevation="2"
  >
    <v-card-title><h1 class="mt-5" style="font-size: 1.5em;">What's On Your Mind</h1></v-card-title>
    <v-form
        ref="form"
    >
      <v-card-text>
        <v-textarea
            v-model="text"
            :rules="textRules"
            auto-grow
            name="input-7-4"
            label="Tweet it out"
        ></v-textarea>
      </v-card-text>

    </v-form>

    <v-card-actions>
      <v-btn
          color="primary"
          class="ma-2 white--text"
          @click="postTweet"
      >
        Tweet
        <v-icon
            right
            dark
        >
          mdi-cloud-upload
        </v-icon>
      </v-btn>
    </v-card-actions>
  </v-card>
</template>
<script>
import api from "../services/api"
import cookies from "vue-cookies"

export default {
  name: 'tweet',
  data() {
    return {
      text: "",
      textRules: [
        value => !!value || 'Required.',
      ]
    }
  },
  methods: {

    post(){
      aixos.request({
        url: "https://mini.ml/api/blogs",
        method: "GET",
        headers: {
          "Content-Type": "application/json"
        },
      }).then((response) => {
        console.log(response)
      }).catch((error) => {
        console.log(error)
      })
    },


    postTweet(){
      axio.request({
        url: "https://mini.ml/api/blogs",
        method: "POST",
        headers: {
          "Content-Type": "application/json"
        },
        data: {
          "id" : "id",
          "content": "content",
          "loginToken": "loginToken"
        },
      }).then((response) => {
        console.log(response)
      }).catch((error) => {
        console.log(error)
      })
    },

    updateTweet(){
      axio.request({
        url: "https://mini.ml/api/blogs",
        method: "PATCH",
        headers: {
          "Content-Type": "application/json"
        },
        data: {
          "id" : "id",
          "content": "content",
          "loginToken": "loginToken"

        },
      }).then((response) => {
        console.log(response)
      }).catch((error) => {
        console.log(error)
      })
    },

    deteleTweet(){
      axio.request({
        url: "https://mini.ml/api/blogs",
        method: "DELETE",
        headers: {
          "Content-Type": "application/json"
        },
        data: {
          "id" : "id",
          "content": "content",
          "loginToken": "loginToken"
        },
      }).then((response) => {
        console.log(response)
      }).catch((error) => {
        console.log(error)
      })
    },
  }} 

  
  


</script>