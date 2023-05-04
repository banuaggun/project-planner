<template>
    <div class="project">
        <div class="actions">
            <h3 @click="showDetails = !showDetails">{{ project.title }}</h3>
        </div>
        <div class="details" v-if="showDetails">
            <p>{{ project.details }}</p>
        </div>
    </div>
</template>
<script>
export default {
    props: ["project"],
    data(){
      return{
        showDetails:false
      }
    }
};
</script>
<style>
.project{
  margin:20px auto;
  background-color:#fff;
  padding:10px 20px;
  border-radius:0 5px 5px 0;
  box-shadow:1px 2px 3px rgba(0, 0, 0, 0, 0.05);
  border-width:1px 1px 1px 4px;
  border-style:solid;
  border-color:#e90074; 
  width:600px;
}
h3{
  cursor:pointer;
}
</style>
