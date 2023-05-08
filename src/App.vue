<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <header>

    <div class="wrapper">
      <nav>
        <RouterLink to="/">Home</RouterLink>
        <RouterLink to="/add">Add Project</RouterLink>
      </nav>
    </div>
  </header>

  <RouterView />
</template>

<style>
header{
  display:flex;
  align-items: center;
  width:100%;
  height:110px;
}
</style>
