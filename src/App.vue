<template>
  <header>       
    <div class="wrapper">
      <Navtitle/>
      <Navbar/>
    </div>
  </header>

  <RouterView />
</template>
<script>
import Navbar from "./components/Navbar.vue";
import Navtitle from "./components/Navtitle.vue";
export default {
  components:{Navbar, Navtitle}
}
</script>

<style>

</style>
