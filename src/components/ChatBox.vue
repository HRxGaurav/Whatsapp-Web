<template >
    <div>
        <h1 v-for="chat in msg" :key="chat">
            {{chat}}
        </h1>
    </div>
</template>
<script>
export default {
    name:"ChatBox",
    props:{
        msg:Array,
    }
}
</script>
<style >
    
</style>