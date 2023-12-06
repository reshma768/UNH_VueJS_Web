<template>
    <div>
        <h2> {{foodName}}</h2>
        <h2>{{foodNames}} </h2>
        
    </div>
</template>

<script>

    export default{
        name: 'MyHeader',
        props:{
            foodName: String,
            foodNames: String
        }

    }
 
</script>

<style scoped>
    div{
        text-align: center;
    }
</style>
