<script>
import header from './header.vue';
import team from './team.vue';
export default{
    name: "first",
    components:{
        Header:header,
        Team:team
    },
    mounted(){
        window.addEventListener("load", ()=>{
            window.scrollTo(0,0);
        });
    }
}
</script>
<template>
    <Header />
    <Team />
</template>