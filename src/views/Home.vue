<template>
  <div class="home h-100">
    <!--   <the-home>
    </the-home> -->
    <nav-bar> </nav-bar>
    <div class="container-fluid h-100">
      
      <div class="row h-100 ">
            <button
      class="navbar-toggler position-absolute d-md-none collapsed"
      type="button"
      data-toggle="collapse"
      data-target="#sidebarMenu"
      aria-controls="sidebarMenu"
      aria-expanded="false"
      aria-label="Toggle navigation"
    >
      <span class="navbar-toggler-icon"></span>
    </button>
        <nav
          id="sidebarMenu"
          class="col-md-3 col-lg-2 d-md-block bg-light sidebar collapse p-0"
        >
  
          <div class="sidebar-sticky pt-1 ">
            <div class="card m-0 p-0 bg-secondary  text-white" >
              <div class="card-header p-1 m-0">{{ user.name }}</div>
              <div class="card-body p-0 m-0">{{ user.email }}</div>
              
            </div>
            <ul class="nav flex-column mt-4">
              <li class="nav-item">
                <a class="nav-link active" href="#">
                  <span data-feather="home"></span>
                  Dashboard <span class="sr-only">(current)</span>
                </a>
              </li>
              <li class="nav-item">
                <a class="nav-link" href="#">
                  <span data-feather="file"></span>
                  Orders
                </a>
              </li>
              <li class="nav-item">
                <a class="nav-link" href="#">
                  <span data-feather="shopping-cart"></span>
                  Products
                </a>
              </li>
              <li class="nav-item">
                <a class="nav-link" href="#">
                  <span data-feather="users"></span>
                  Customers
                </a>
              </li>
              <li class="nav-item">
                <a class="nav-link" href="#">
                  <span data-feather="bar-chart-2"></span>
                  Reports
                </a>
              </li>
              <li class="nav-item">
                <a class="nav-link" href="#">
                  <span data-feather="layers"></span>
                  Integrations
                </a>
              </li>
            </ul>
          </div>
        </nav>

        <main role="main" class="col-md-9 ml-sm-auto col-lg-10 px-md-4">
          <div
            class="d-flex justify-content-between align-items-center pt-3 pb-2 mb-3 bg-info h-100"
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
