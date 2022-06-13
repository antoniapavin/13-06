<script setup>
import HeaderComp from "@/components/template/HeaderComp.vue";
import RodapeComp from "@/components/template/RodapeComp.vue";
</script>
<template>
  <HeaderComp />
  <main>
   <RouterView /> 
  </main>
  <RodapeComp />
</template>

<style>
@import "@/assets/base.css";
@import "@/assets/style.css";
#app {
  max-width: 1280px;
  margin: 0 auto;
  /*padding: 2rem; */
  height: 100vh;
  font-weight: normal;
  background-color: #dddddd;
}

header,
footer {
  background-color: #143265;
  color: white;
  height: 15%;
  font-size: 1.3rem;
  display: flex;
  align-items: center;
  padding-left: 2rem;
}


main {
  height: 70%;
}
</style>
