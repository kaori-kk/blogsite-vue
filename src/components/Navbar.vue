<template>
  <nav class="navbar navbar-expand-lg navbar-light bg-light">
  <router-link class="navbar-brand" to="/">
    <img src="../assets/logo.png" width="30px" height="30px" alt="">
  </router-link>
  <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
    <span class="navbar-toggler-icon"></span>
  </button>

  <div class="collapse navbar-collapse" id="navbarSupportedContent">
    <ul class="navbar-nav mr-auto">
      <li class="nav-item active">
        <a class="nav-link" href="/">Home <span class="sr-only">(current)</span></a>
      </li>
      <li class="nav-item">
        <router-link class="nav-link" to="/login">Login</router-link>
      </li>
      <li class="nav-item">
        <router-link class="nav-link" to="/signup">Signup</router-link>
      </li>
      <li class="nav-item dropdown" v-if="$root.auth.user">
        <a class="nav-link dropdown-toggle" href="#" id="navbarDropdown" role="button" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
          Hey {{$root.auth.user.name}}
        </a>
        <div class="dropdown-menu" aria-labelledby="navbarDropdown">
          <a class="dropdown-item" @click="logout()" href="#">Logout</a>
        </div>
      </li>
    </ul>
  </div>
  </nav>
</template>

<script>
export default {
  mounted(){
    console.log(this.$root)
  },
  methods: {
    logout(){
      localStorage.removeItem("auth")
      this.$root.auth = {}
    }
  }
}
</script>