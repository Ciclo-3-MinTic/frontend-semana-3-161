<template>
  <div class="pt-5 vh-100">
    <!--   <the-home>
    </the-home> -->
    <nav-bar> </nav-bar>
    <div class="container-fluid h-100 ">
      
      <div class="row h-100">
      
        <nav
          id="sidebarMenu"
          class="col-md-3 col-lg-2 d-md-block sidebar collapse p-0 h-sm-100 bg-transparent"
        >
  
          <div class="sidebar-sticky pl-3">
            <div class="card m-0 p-0  border-light text-white bg-transparent" >
              <div class="card-header p-1 m-0">{{ user.name }}</div>
              <div class="card-body p-0 m-0">{{ user.email }}</div>
              
            </div>
            <div class="list-group mt-3 bg-transparent">
            <button class="list-group-item-action d-flex justify-content-between btn btn-light mb-1" type="button">
                  Lorem.
                  <span class="badge badge-info badge-pill ">14</span> 
            </button>
            <button class="list-group-item-action d-flex justify-content-between  btn btn-light" type="button">
                  Lorem.
                  <span class="badge badge-danger badge-pill">3</span> 
            </button>
           
            </div>
            <div class="list-group mt-3">
            <button class="list-group-item list-group-item-action " type="button">
                  Lorem, ipsum.
                  
            </button>
            <button class="list-group-item list-group-item-action " type="button">
                  Lorem, ipsum. 
            </button>
            <button class="list-group-item list-group-item-action " type="button">
                  Lorem, ipsum. 
            </button>
            <button class="list-group-item list-group-item-action " type="button">
                  Lorem, ipsum.  
            </button>
            <button class="list-group-item list-group-item-action " type="button">
                  Lorem, ipsum.  
            </button>
            </div>
              
          </div>
        </nav>

        <main role="main" class="col-md-9 ml-sm-auto col-lg-10 px-md-4 ">
          <div
            class="d-flex justify-content-between align-items-center pt-3 pb-2 mb-3 bg-secondary h-100"
          ></div>
        </main>
      </div>
    </div>
  </div>
</template>

<script>
import NavBar from "../components/NavBar.vue";
// @ is an alias to /src

import TheHome from "../components/TheHome.vue";
import VueJwtDecode from "vue-jwt-decode";
export default {
  name: "Home",
  components: {
    TheHome,
    NavBar,
  },
  data() {
    return {
      user: {},
    };
  },

  methods:{
    getUserDetails() {
      let token = localStorage.getItem("jwt");
      let decoded = VueJwtDecode.decode(token);
      console.log("hola decode", decoded);
      this.user = decoded;
    },
  },
  created() {
    this.getUserDetails();
  },
};
</script>
<style scoped>

</style>
