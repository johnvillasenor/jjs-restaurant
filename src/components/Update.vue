<template>
<HeaderTop />
<h1>Welcome, this is the Update page</h1>
</template>
<script>
import HeaderTop from './Header.vue'
export default {
    name:'UpdatePage',
    components: {
        HeaderTop
    },
    mounted()
    {
        let user= localStorage.getItem('user-info');
        if(!user)
        {
            this.$router.push({name:'SignUp'})
        }
    }
}
</script>
