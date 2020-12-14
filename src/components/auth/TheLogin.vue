<template>
  <div class="row justify-content-center pt-5 ">
    <div class="card border-0 col col-sm-10 col-md-8 col-lg-4 mx-5 bg-transparent">
      <div class="card-header bg-transparent border-0 ">
        <img
          alt="logo-login"
          src="@/assets/login.svg"
          class="w-50 img-fluid d-sm-none d-lg-inline"
        />
        <img
          alt="logo-login"
          src="@/assets/login.svg"
          class="w-25 img-fluid d-lg-none d-sm-inline d-none"
        />
      </div>
      <div class="row bg-blue">
        <div class="card-body border col bg-transparent rounded shadow ">
          <form @submit.prevent="loginUser">
            <!-- user -->
            <div class="input-group form-group">
              <div class="input-group-prepend">
                <span class="input-group-text bg-yellow">
                  <img
                    alt="Vue logo"
                    src="@/assets/user.svg"
                    class="icon-input img-fluid"
                  />
                </span>
              </div>
              <input
                type="text"
                id="email"
                class="form-control"
                placeholder="Email"
                v-model="login.email"
              />
            </div>
            <!-- password -->
            <div class="input-group form-group">
              <div class="input-group-prepend">
                <span class="input-group-text bg-yellow">
                  <img
                    alt="Vue logo"
                    src="@/assets/key.svg"
                    class="icon-input img-fluid"
                  />
                </span>
              </div>
              <input
                type="password"
                id="password"
                class="form-control"
                placeholder="password"
                v-model="login.password"
              />
            </div>

            <div class="form-check form-group d-flex justify-content-between">
              
              <input class="form-check-input " type="checkbox" name="Remember" id="Remember" disabled/>
              <label class="form-check-label text-dark" for="Remember">
                Remember Me
              </label>
              <input
                type="submit"
                value="Login"
                class="btn  bg-yellow float-right"
              />
            </div>
            
          </form>
        </div>
      </div>
      <!-- footer card, recuperar contraseña y registrase -->
      <!-- <div class="card-footer">
				<div class="d-flex justify-content-center links">
					Don't have an account?<a href="#">Sign Up</a>
				</div>
				<div class="d-flex justify-content-center">
					<a href="#">Forgot your password?</a>
				</div>
			</div> -->
    </div>
  </div>
</template>
<script>
import swal from "sweetalert";
export default {
  data() {
    return {
      login: {
        email: "",
        password: "",
      },
    };
  },
  methods: {
    async loginUser() {
      try {
        let response = await this.$http.post("/api/auth/signin", this.login);
        console.log(response.data);
        let token = response.data.accessToken;
        localStorage.setItem("jwt", token);
        if (token) {
          swal("Exitoso", "login exitoso", "success");
          this.$router.push("/home");
        }
      } catch (err) {
        swal("Error", "datos incorrectos", "error");
        console.log(err.response);
      }
    },
  },
};
</script>

<style scoped>

.bg-blue{
  background-color: rgba(111, 227, 255, 0.7);
 
}
.bg-yellow{
  background-color: rgb(248, 236, 125);

}
.bg-yellow:hover{
  background-color: rgb(255, 201, 164);

}


.input-group-prepend span {
  width: 50px;

  border: 0 !important;
}
.icon-input {
  width: 25px;
  max-width: min-content;
}

input:focus {
  outline: 0 0 0 0 !important;
  box-shadow: 0 0 0 0 !important;
}


</style>
