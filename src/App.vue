<template>
  <div id="app">
    <TheHeader/>
    <router-view class="container"></router-view>
  </div>
</template>

<script>
import TheHeader from "@/components/TheHeader.vue";


export default {
  components: {
    TheHeader
  }
};
</script>


<style>
 html, body {
  height: 100%;
 }
 
 body {
  min-height: 100%;
  background: rgb(26, 30, 39);
  margin: 0px;
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  color: rgb(255, 255, 255);
 }

 p {
  color: rgb(159, 158, 158);
 }
 ul {
  list-style: none;
  padding: 0px;
  margin: 0px;
 }
 a {
  font-weight: bold;
  text-decoration: none;
  color: rgb(254, 255, 255);
 }
 img {
  max-width: 100%;
 }
 
 .container {
  max-width: 800px;
  margin: 0 auto;
  padding: 20px;
 }

 .v-enter {
  opacity: 0;
  transform: translate3d(-20px,0,0) 
 }

 .v-enter-active {
  transition: all .3s;
 }

 .conteudo {
  display: grid;
  grid-template-columns: 1fr minmax(200px, 400px);
  grid-gap: 30px;
 }

 @media screen and (max-width: 420px) {
  .conteudo {
    display: block;
  }
 }
</style>
