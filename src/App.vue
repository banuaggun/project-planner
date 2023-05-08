

<template>
  <header>

    <div class="wrapper">
      <Navbar/>
    </div>
  </header>

  <RouterView />
</template>
<script>
import Navbar from "./components/Navbar.vue";
export default {
  components:{Navbar}
}
</script>

<style>
header{
  display:flex;
  align-items: center;
  width:100%;
  height:110px;
}
</style>
