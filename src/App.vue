<template>
  <router-view />
</template>

<script>
export default {
  name: 'App',

}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

body{
  padding:0;
  margin:0;
}

.logo{
    width:300px;
}

.register input, .login input{
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

.register button, .login button{
    width: 100px;
    height: 20px;
    border: 1px solid skyblue;
    color: black;
    cursor: pointer;
}
</style>
