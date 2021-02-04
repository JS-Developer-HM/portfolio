<template>
  <div id="root" v-if="reactive.data.length">
    <the-header></the-header>
    <my-portfolio></my-portfolio>
  </div>
</template>

<script>
import firebase from "firebase/app";

import "firebase/auth";
import "firebase/database";
import "firebase/storage";

var firebaseConfig = {
  apiKey: "AIzaSyDOKGLDvhxAy_rsCl8_jf_Kk8MP7sIl8hc",
  authDomain: "portfolio-d4ebf.firebaseapp.com",
  databaseURL: "https://portfolio-d4ebf-default-rtdb.firebaseio.com",
  projectId: "portfolio-d4ebf",
  storageBucket: "portfolio-d4ebf.appspot.com",
  messagingSenderId: "112231391662",
  appId: "1:112231391662:web:f7ddd2264fc1f83278683f",
};
// Intialize Firebase
firebase.initializeApp(firebaseConfig);
var database = firebase.database();

import TheHeader from "./components/header";
import MyPortfolio from "./components/portfolio";
export default {
  components: { TheHeader, MyPortfolio },
  provide() {
    return {
      reactive: this.reactive,
    };
  },

  data() {
    return {
      reactive: {
        data: [],
      },
    };
  },
  created() {
    database
      .ref("data")
      .once("value")
      .then((data) => {
        this.reactive.data = data.val().filter((e) => e);
      });
  },
};
</script>
