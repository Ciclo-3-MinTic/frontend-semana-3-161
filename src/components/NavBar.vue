<template>
  <nav class="navbar navbar-dark bg-dark  p-0 position-fixed fixed-top d-inline-flex">
    
      <button
      class="navbar-toggler  d-md-none collapsed d-inline"
      type="button"
      data-toggle="collapse"
      data-target="#sidebarMenu"
      aria-controls="sidebarMenu"
      aria-expanded="false"
      aria-label="Toggle navigation"
    >
      <span class="navbar-toggler-icon"></span>
    </button>
    <spam class="navbar-brand col-3 col-lg-2 mr-0 px-3 "
      >Company name</spam>

    <ul class="navbar-nav px-3">
      <li class="nav-item ">
        <button class="nav-link btn btn-sm btn-danger m-0 py-1 px-2 "  @click="logUserOut">Sign out</button>
      </li>
    </ul>
  </nav>
</template>

<script>
import VueJwtDecode from "vue-jwt-decode";
export default {
  
  methods: {
    
    logUserOut() {
      localStorage.removeItem("jwt");
      this.$router.push("/");
    },
  },
  
};
</script>

<style>
</style>