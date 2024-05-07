<script setup>

</script>

<template>
  <nav class="navbar navbar-expand-lg bg-body-tertiary">
    <div class="container-fluid">
      <router-link :to="{name: 'home'}" class="navbar-brand">Navbar</router-link>
      <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarNav">
        <ul class="navbar-nav">
          <li class="nav-item">
            <router-link :to="{ name: 'home'}" class="nav-link text-center" :class="{ 'active text-bold text-bg-info' : $route.name === 'home'  }">Home</router-link>
          </li>
          <li class="nav-item">
            <router-link :to="{ name: 'About'}" class="nav-link text-center" :class="{ 'active text-bold text-bg-info' : $route.name === 'About'  }">About</router-link>
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<style scoped>

</style>