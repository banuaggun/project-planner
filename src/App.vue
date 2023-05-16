<template>
  <header>
      <span>Project Planner</span>
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
header span{
  height:60px;
  display:flex;
  justify-content: flex-start;
  padding-left:20px;
align-items:flex-end;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  font-size:1.8rem;
  font-weight:700;
  letter-spacing:0.8px;
}
</style>
