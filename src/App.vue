<template>
  <siteHeader></siteHeader>
  <SiteNavbar></SiteNavbar>
  <main>
    <SiteVideojuegos></SiteVideojuegos>
    <div class="adminNewsTable">
      <SiteTrucos></SiteTrucos>
      <SiteNoticias></SiteNoticias>
    </div>
    
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
#app {
  font-family: 'Maven Pro', sans-serif;
  background-color: #000000;
  
}
main{
  margin: 0px;
  padding: 0px;
  width: 100%;
  display: flex; 
  flex-wrap: wrap;
}
form button{
  border-radius: 10px;
  height: 40px;
}
button{
    width: 50%;
}
.adminNewsTable{
  display: flex;
}

</style>
