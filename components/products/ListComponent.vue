<template>
    <div class="Post">
            
        <div class="Body" v-for="p in post" :key="p.id" >
            <h2>{{ p.title }}</h2>
            <p>{{ p.body }}</p>
        </div>
            
    </div>
</template>

<style lang="scss">
    @import './ListComponent.scss';
</style>

<script lang="ts">
  export default{
    
    data(){
        return{
            post:<any>[],
            api:<string> "https://jsonplaceholder.typicode.com/posts?userId=1"
        }
    },
    methods:{
        getPosts(){
            fetch(this.api)
            .then(reponse => reponse.json())
            .then(data => this.post = data)
        },
    },
    mounted(){
        this.getPosts()
    },
  }
</script>