<template>
  <div id="app">
    <div>
    <router-view/>

    </div>
    
  </div>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  
  background-image: url("http://getwallpapers.com/wallpaper/full/a/5/d/544750.jpg");
  background-size: cover;
  height: 100%;
  min-height: 100vh;
}


#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}

</style>
