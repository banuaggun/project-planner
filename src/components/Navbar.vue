<template>
  <nav class="main-nav">
    <div class="main-nav-left">
    <router-link :to="{name:'Home'}">Projects</router-link>
    <router-link :to="{name:'AddProject'}">New Project</router-link>
    </div>
    <div class="main-nav-right">
      <a href="https://github.com/banuaggun/project-planner" target="_blank">Github</a>
    </div>
  </nav>
</template>
<script>
export default {
  
}
</script>
<style>
  .main-nav{
    display:flex;
    justify-content:space-between;
    align-items:center;
    border:1px solid green;
    width:100%;
    font-weight: 600;
    height:110px;
  }
  .main-nav a{
    display:inline-block;
    text-decoration: none;
    margin:0 10px;
    color:#635e5e;
    padding:4px;
    font-size:1.3rem;
  }
  a.router-link-active{
    border-bottom:2px solid #59b65a;
    padding-bottom:4px;
    color:#59b65a;
    font-weight:600;
    letter-spacing:0.8px;
  }

  @media (max-width:500px){
    .main-nav{
      width:100%;
      height:80px;
      background:blue;
    }
    .main-nav a{
      font-size:14px;
    }
  }
</style>