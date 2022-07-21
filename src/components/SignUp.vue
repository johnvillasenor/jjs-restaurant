<template>
<img class="logo" src="../assets/logo2.png" />
<h1>Sign Up</h1>
<div class="register">
    <input type="text" v-model="name" placeholder="Enter Name" />
    <input type="text" v-model="email" placeholder="Enter Email" />
    <input type="password" v-model="password" placeholder="Enter Password" />
    <button v-on:click="signUp">Sign Up</button>
    <p>
        <router-link to="/login" >Login</router-link>
    </p>
</div>
</template>
<script>
import axios from 'axios'
export default {
    name:'SignUp',
    data()
    {
        return {
            name:'',
            email:'',
            password:''
        }
    },
    methods:{
        async signUp()
        {
            let result = await axios.post("http://localhost:3000/users",{
                name:this.name,
                email:this.email,
                password:this.password
            });

            console.warn(result);
            if(result.status==201)
            {
                localStorage.setItem("user-info",JSON.stringify(result.data))
                this.$router.push({name:'HomePage'})
            }
        }
    },
    mounted()
    {
        let user= localStorage.getItem('user-info');
        if(user)
        {
            this.$router.push({name:'HomePage'})
        }
    }
}
</script>

<style>
.logo{
    width:300px;
}

.register input{
    width: 150px;
    height: 20px;
    padding-left: 15px;
    padding-right: 15px;
    display: block;
    margin-bottom: 30px;
    margin-right: auto;
    margin-left: auto;
    border: 1px solid skyblue;
}

.register button{
    width: 100px;
    height: 20px;
    border: 1px solid skyblue;
    color: black;
    cursor: pointer;
}
</style>