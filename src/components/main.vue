<template>
    <div>
        {{msg}}
    </div>
</template>
<script>
export default {
    props:{
        user_id:String
    },
    data:function(){
        return {
            msg: this.$route.params.user_id
        }
    }
}
</script>
<style scoped>
    div{
        background-color: antiquewhite;
        height:100vh;
    }
</style>

