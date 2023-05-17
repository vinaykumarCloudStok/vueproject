<template>
    <form action="" class="form-container" on-submit="">
       <div class="form-head">
        <h2>Sign Up</h2>
      <div class="input-head">
        <div class="input-container">
  <label for="name">Name</label> <br>
  <input type="text" placeholder="enter name" name="" v-model="user.name" id="name">
        </div>
        <div class="input-container">
  <label for="email">Email</label> <br>
  <input type="email" placeholder="@gmail.com" name="" v-model="user.email" id="email">
        </div>
        <div class="input-container">
  <label for="email">Password</label> <br>
  <input type="password" name="" placeholder="******" v-model="user.password" id="password">
        </div>
        <div class="btn">
            <button type="button" v-on:click="getData">Register</button>
        </div>
      </div>
       </div>
    </form>
</template>
<script>
export default {
    name:"SignUp",
    data(){
        return{
            user:{
                name:"",
                email:"",
                password:""
            }
        }
    },
    methods:{
       async getData(){
            const res  = await fetch ('http://localhost:3000/user',{
                method:"POST",
                headers:{
                    'Content-Type':"application/json"
                },
                body:JSON.stringify(this.user)
            })
            console.log(res)
        }
    }
    
}
</script>
