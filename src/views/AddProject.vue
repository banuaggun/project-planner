<template>
  <form @submit.prevent="handleSubmit">
    <label>Title</label>
    <input type="text" v-model="title" required>
    <label>Details</label>
    <textarea v-model="details" required></textarea>
    <button>Add project</button>
  </form>
</template>
<script>
export default {
  data(){
    return{
      title:'',
      details:''
    }
  },
  methods:{
    handleSubmit(){
      let project = {
        title:this.title,
        details:this.details,
        complete:false
      }
      fetch('http://localhost:3000/projects', {
        method:'POST',
        headers:{"Content-Type": "application/json"},
        body:JSON.stringify(project)
      }).then(() => this.$router.push('/')).catch(err => console.log(err));
    }
  }
}
</script>
<style>
form{
  background:#fff;
  padding:20px;
  border-radius:10px;
}
label{
  display:block;
  color:darkgray;
  text-transform:uppercase;
  font-size:14px;
  font-weight:bold;
  letter-spacing:1px;
  margin:20px 0 10px 0;
}
input{
  padding:10px;
  border:0;
  border-bottom:2px solid darkgray;
  box-sizing:border-box;
  width:100%;
  background:none;
}
textarea{
  border:2px solid darkgray;
  padding: 10px;
  width:100%;
  box-sizing:border-box;
}
form button{
  display:block;
  margin:20px auto 0;
  background:#76dd78;
  color:#151515;
  padding:10px 20px;
  border:0;
  border-radius:7px;
  font-size:14px;
  font-weight:600;
}
</style>

