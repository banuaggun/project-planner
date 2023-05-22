<template>
    <nav class="filter-nav">
        <button @click="updateFilter('all')" :class="{active:current === 'all'}">All</button>
        <button @click="updateFilter('completed')" :class="{active:current === 'completed'}">Complete</button>
        <button @click="updateFilter('ongoing')" :class="{active:current === 'ongoing'}">Ongoing</button>
    </nav>
</template>
<script>
export default {
  props:['current'],
    methods: {
        updateFilter(by) {
            this.$emit("filterChange", by);
        },
    },
};
</script>
<style>
.filter-nav{
  margin:60px 0 20px 20px;
}
.filter-nav button{
  padding:15px 30px;
  background:none;
  border:none;
  color:#4b4949;
  outline:none;
  font-size:14px;
  text-transform:uppercase;
  font-weight:bold;
  text-align:center;
  border-radius:20px;
  border:1px solid rgba(142, 142, 142, 0.8);
  cursor:pointer;
}
.filter-nav button:nth-child(1),
.filter-nav button:nth-child(2){
  margin-right:20px;
}
.filter-nav button.active{
  color:#000;
  background-color:#9866b9;
}

@media (max-width:700px){
  .filter-nav{
    overflow-x:hidden;
    margin:40px 8px 20px 8px;
    display:flex;
    justify-content: flex-start;
  }
  .filter-nav button{
    text-align:center;
    padding:10px 15px;
  }
  .filter-nav button:nth-child(1),
.filter-nav button:nth-child(2){
  margin-right:3px;

}
}
</style>
