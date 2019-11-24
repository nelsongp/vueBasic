<template>
    <div>
        <div>
            <h1>{{msg}}</h1>
        </div>
    </div>
</template>
<script>
export default {
    props:{
        msg: String
    },
    created(){
        console.log("created function now available");
    }
};
</script>