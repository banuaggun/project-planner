<template>
  <div class="edit-project">
    <form @submit.prevent="handleEdit">
        <label>Title</label>
        <input type="text" v-model="title" required />
        <label>Details</label>
        <textarea v-model="details" required></textarea>
        <button>UpdateProject</button>
    </form>
  </div>
</template>
<script>
export default {
    props: ["id"],
    data() {
        return {
            title: "",
            details: "",
            uri: "http://localhost:3000/projects/" + this.id,
        };
    },
    mounted() {
        fetch(this.uri)
            .then((res) => res.json())
            .then((data) => {
                this.title = data.title;
                this.details = data.details;
            });
    },
    methods: {
        handleEdit() {
            fetch(this.uri, {
              method: "PATCH",
              headers: { "Content-Type": "application/json" },
              body: JSON.stringify({
                  title: this.title,
                  details: this.details,
              }),
            })
              .then(() => this.$router.push("/"))
              .catch((err) => console.log(err));
        },
    },
};
</script>
<style>
.edit-project{
  width:100%;
  display:flex;
  justify-content:center;
  align-content:center;
}
.edit-project form{
  background-color:#fff;
  padding:20px;
  border-radius:5px;
  box-shadow: 3px -3px 3px rgba(235, 206, 247, 1), -4px 4px 3px rgba(235, 206, 247, 1);
  max-width:800px;
  width:100%;
  margin:20px auto;
}
label{
  display:block;
  color:#4b4949;
  text-transform:uppercase;
  font-size:1rem;
  font-weight:bold;
  letter-spacing:0.6px;
  margin:40px 0 15px 0;
}
input{
  padding:10px;
  border:0;
  border-bottom:3px solid rgba(75, 73, 73, 0.8);
  box-sizing:border-box;
  width:100%;
  background:none;
  outline:none;
}
textarea{
  outline:none;
  border:3px solid rgba(75, 73, 73, 0.8);
  padding: 10px;
  width:100%;
  height:300px;
  box-sizing:border-box;
  font-size:1rem;
  color:#4b4949;
  resize:none;
}
form button{
  display:block;
  margin:20px auto 20px;
  background:#9866b9;
  color:#151515;
  padding:16px 84px;
  border:0;
  text-transform: capitalize;
  letter-spacing:0.6px;
  border-radius:7px;
  font-size:1rem;
  font-weight:600;
  cursor:pointer;
}
@media (max-width:1100px){
  .edit-project form {
    width:100%;
    min-width:270px;
    padding:5px;
    margin:20px 40px;
    display:block;
  }
}
</style>
