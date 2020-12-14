<template>
  <div class="pt-5">
   
    <nav-bar> </nav-bar>
    <div class="container-fluid ">
      
      <div class="row ">
      <sidebar-menu>
      </sidebar-menu>
      <main role="main" class="col-md-9 ml-sm-auto col-lg-10 px-md-4 mt-3 mt-md-0">
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
