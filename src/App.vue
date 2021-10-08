<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <h1>Hello world from {{ name }}</h1>
  <!--  <img v-bind:src="img" v-bind:alt="`alt is:${alt}`" />-->
  <img :src="img" :alt="`alt is:${alt}`" />
  <!--  <button v-on:click="changeName">change name</button>-->
  <button @click="changeName($event, 213)">change name</button>
  <!--  <Button :text="`my awesome button`" :onClick="changeName" />-->
  <Button :text="`my awesome button`" @button-click="changeName" />
  <!--  <button @click="name = Math.floor(Math.random() * 1000)">change name</button>-->
</template>

<script>
import Button from "./components/Button";

export default {
  name: "App",
  components: { Button },
  data() {
    return {
      name: "Ivan",
      img: "http://www.mandysam.com/img/random.jpg",
      alt: "simpson"
    };
  },

  methods: {
    changeName(arg, event) {
      // console.log(this);
      console.log(arg, event);
      this.name = Math.floor(Math.random() * 1000);
    }
  }
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
