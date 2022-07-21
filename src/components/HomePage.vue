<template>
<HeaderTop />
<h1>Welcome {{name}}, hope you're hungry!</h1>
</template>
<script>
import HeaderTop from './Header.vue'
export default {
    name:'HomePage',
    data()
    {
        return {
            name:''
        }
    },
    components: {
        HeaderTop
    },
    mounted()
    {
        let user= localStorage.getItem('user-info');
        this.name= JSON.parse(user).name;
        if(!user)
        {
            this.$router.push({name:'SignUp'})
        }
    }
}
</script>
