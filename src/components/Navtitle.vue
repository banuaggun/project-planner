<template>
  <div class="title-area">
    <div class="title-area-left">
      <span>Project Planner</span>
    </div>
    <div class="title-area-right">
      <a href="https://github.com/banuaggun/project-planner" target="_blank">
        <i class="fa fa-github"></i>
      </a>
      <a href="https://www.linkedin.com/in/banuaggun/?locale=en_US" target="_blank">
        <i class="fa fa-linkedin"></i>
      </a>
    </div>
  </div>
</template>
<script>
export default {
  
}
</script>
<style>
.title-area{
  display:flex;
  flex-direction: column;
}
.title-area-left span{
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
.title-area-right{
  display:flex;
  justify-content:flex-end;
  align-items:flex-end;
}
.title-area-right a{
  display:inline-block;
  text-decoration: none;
  margin:0 10px;
  padding:8px;
}
.title-area-right a i{
  font-size:1.2rem;
  color:#4b4949;
}
@media (max-width:700px){
  .title-area-right{
    padding-right:20px;
    border:1px solid blue;
  }
  .title-area a{
    font-size:14px;
    margin:0 5px;
    padding:2px;
  }
}
@media (min-width:701px) and (max-width:1100px){
  .title-area-right{
    padding-right:20px;
  }
}
</style>