<template>
    <div class="project" :class="{ complete: project.complete }">
        <div class="actions" @click="showDetails = !showDetails">
            <h3>{{ project.title }}</h3>
            <div class="icons">
                <router-link :to="{name:'EditProject', params:{id:project.id}}">
                    <span class="material-icons edit">edit</span>
                </router-link>
                <span class="material-icons delete" @click="deleteProject">
                    delete
                </span>
                <span class="material-icons tick" @click="toggleComplete"
                    >done</span
                >
                
            </div>
        </div>
        <div class="details" v-if="showDetails">
            <p>{{ project.details }}</p>
        </div>
    </div>
</template>
<script>
export default {
    props: ["project"],
    data() {
        return {
            showDetails: false,
            uri: "http://localhost:3000/projects/" + this.project.id,
        };
    },
    methods: {
        deleteProject() {
            fetch(this.uri, { method: "DELETE" })
                .then(() => this.$emit("delete", this.project.id))
                .catch((err) => console.log(err));
        },
        toggleComplete() {
            fetch(this.uri, {
                method: "PATCH",
                headers: { "Content-Type": "application/json" },
                body: JSON.stringify({ complete: !this.project.complete }),
            })
            .then(() => this.$emit("complete", this.project.id))
            .catch((err) => console.log(err));
        },
    },
};
</script>
<style>
.project {
    display:flex;
    flex-direction:column;
    justify-content:center;
    margin: 40px auto;
    background-color: #fff;
    padding: 10px 20px;
    border-radius: 0 5px 5px 0;
    box-shadow: 1px 4px 3px rgba(0, 0, 0, 0.08);
    border-width: 1px 1px 1px 8px;
    border-style: ridge;
    border-color: rgba(142, 142, 142, 0.8);
    max-width: 600px;
    width:100%;
}
.project:hover{
    cursor:pointer;
    border-color:rgba(152, 102, 185, 0.4);
    background-color:rgba(152, 102, 185, 0.5);
    transition:all 0.2s;
}

@media (max-width:700px){
    .project{
        
        margin:40px auto;
        width:calc(100% - 70px);
    }
}

h3 {
    text-transform:capitalize;
    cursor: pointer;
}
.details p::first-letter{
    text-transform:capitalize;
}
.actions {
    display: flex;
    justify-content: space-between;
    align-items: center;
}
.material-icons {
    font-size: 24px;
    margin-left: 10px;
    color: #555;
    cursor: pointer;
}
.edit:hover{
    color:darkorange;
}

.delete:hover{
    color:darkred;
}

.tick{
    font-weight:bold;
}

.project.complete {
    border-left: 8px solid mediumseagreen;
}
.project.complete .tick {
    color: mediumseagreen;
}
</style>
