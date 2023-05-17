<template>
  <nav class="main-nav">
    <router-link :to="{name:'Home'}">Projects</router-link>
    <router-link :to="{name:'AddProject'}">New Project</router-link>
  </nav>
</template>
<script>

export default {
  
}
</script>
<style>
  .main-nav{
    display:flex;
    justify-content:flex-start;
    align-items:center;
    border:none;
    width:100%;
    font-weight: 600;
    height:60px; 
  }
  .main-nav a{
    display:inline-block;
    text-decoration: none;
    margin:0 10px;
    color:#4b4949;
    padding:4px;
    font-size:1.2rem;
  }
  a.router-link-active{
    border-bottom:2px solid #9866b9;
    padding-bottom:4px;
    color:#9866b9;
    font-weight:600;
    letter-spacing:0.8px;
  }

  @media (max-width:700px){
    .main-nav{
      width:100%;
      height:80px;
      padding-left:20px;
    }
    
    .main-nav a{
      font-size:14px;
      margin:0 5px;
      padding:2px;
    }
  }

  @media (min-width:701px) and (max-width:1100px){
    .main-nav{
      padding-left:40px;
    }
  }
</style>