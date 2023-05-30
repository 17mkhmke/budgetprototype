<template>
    <div class="container-fluid px-0">
        <nav class="navbar navbar-expand-lg bg-dark px-1">
  
    <img src="https://i.postimg.cc/Hn3z1K9R/Free-Sample-By-Wix-1.jpg" class="logo" alt="Logo">
    <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="navbarNav">
      <ul class="navbar-nav d-flex justify-content-around w-50 mx-auto">
        <li class="nav-item">
            <router-link to="/">Home</router-link>
        </li>
        <li class="nav-item">
            <router-link to="/budget">Budget</router-link>
        </li>
        <li class="nav-item">
            <router-link to="/about">About</router-link>
        </li>
        <li class="nav-item">
            <router-link to="/contact">Contact</router-link>
        </li>
      </ul>
    </div>

</nav>
    </div>
</template>

<script>
export default{
    name: 'NavBar'
}
</script>

