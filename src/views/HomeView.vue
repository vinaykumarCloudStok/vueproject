<script>
export default {
  name:"HomeView",
  data(){
    return{
      post:[]
    };
  },
  methods:{
   async getData(){
      try{
        const res  = await fetch('https://jsonplaceholder.typicode.com/users',{
          method:"GET"
        })
  this.post = await res.json()
  console.log(this.post)
      } catch(err){
        console.log(err)
      }
    }
  }
}
</script>

<template>
  <section>
    <button v-on:click="getData">Load Data</button>
  <ul>
    <li v-for="item in post" :key="item"> {{ item.name }}  </li>
  </ul>
  </section>
</template>
