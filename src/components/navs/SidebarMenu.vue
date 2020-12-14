<template>
    <nav
          id="sidebarMenu"
          class="col-md-3 col-lg-2 d-md-block sidebar collapse p-0 bg-transparent"
        >
  
          <div class="sidebar-sticky ml-3 mr-md-0 mr-3">
            <div class="card m-0 p-0  border-light text-white bg-transparent" >
              <div class="card-header p-1 m-0">{{ user.name }}</div>
              <div class="card-body p-0 m-0">{{ user.email }}</div>
              
            </div>
            <div class="list-group mt-3 bg-transparent d-md-flex d-inline-flex  flex-row flex-md-column w-100">
            <button class="list-group-item-action d-flex justify-content-between btn btn-light mb-md-1 mx-md-0 mx-4" type="button">
                  Lorem.
                  <span class="badge badge-info badge-pill ">14</span> 
            </button>
            <button class="list-group-item-action d-flex justify-content-between  btn btn-light mx-md-0 mx-4" type="button">
                  Lorem.
                  <span class="badge badge-danger badge-pill">3</span> 
            </button>
           
            </div>
            <div class="list-group mt-3 flex-row flex-md-column ">
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
</template>

<script>
import VueJwtDecode from "vue-jwt-decode";

export default {
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

}
</script>

<style>

</style>