<template>
  <div class="pt-5 vh-100">
   
    <nav-bar> </nav-bar>
    <div class="container-fluid h-100 ">
      
      <div class="row h-100">
      <sidebar-menu>
      </sidebar-menu>
      <main role="main" class="col-md-9 ml-sm-auto col-lg-10 px-md-4 ">
            <the-home>
            </the-home>
        </main>
      </div>
    </div>
  </div>
</template>

<script>
import NavBar from "../components/navs/NavBar.vue";
import SidebarMenu from '../components/navs/SidebarMenu.vue';
// @ is an alias to /src

import TheHome from "../components/seccions/TheHome.vue";
export default {
  name: "Home",
  components: {
    TheHome,
    NavBar,
    SidebarMenu,
  },
  
};
</script>
<style scoped>

</style>
