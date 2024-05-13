<template>
  <siteHeader></siteHeader>
  <SiteNavbar></SiteNavbar>
  <main>
    <SiteVideojuegos></SiteVideojuegos>
    <SiteTrucos></SiteTrucos>
    <SiteNoticias></SiteNoticias>
    <SiteRanking></SiteRanking>
  </main>
  <SiteFooter></SiteFooter>
</template>

<script>

import SiteNavbar from './components/SiteNavbar.vue';
import siteHeader from './components/SiteHeader.vue';
import SiteVideojuegos from './components/SiteVideojuegos.vue';
import SiteTrucos from './components/SiteTrucos.vue';
import SiteNoticias from './components/SiteNoticias.vue';
import SiteRanking from './components/SiteRanking.vue';
import SiteFooter from './components/SiteFooter.vue';


export default {
  name: 'App',
  components: {
    siteHeader,
    SiteNavbar,
    SiteVideojuegos,
    SiteTrucos,
    SiteNoticias,
    SiteRanking,
    SiteFooter
  }
}
</script>

<style>
html, body{
  padding: 0px;
  margin: 0px;
}
#app {
  margin: 0rem;
  padding: 0rem;
  font-family: 'Maven Pro', sans-serif;
  background-color: #000000;
  
}
body{
  margin: 0rem;
  padding: 0rem;
}
main{
  width: 100%;
  display: flex; 
  flex-wrap: wrap;
}
</style>
