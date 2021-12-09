<template >
    <div class="mt-3 flex justify-end mr-20">
        <h1 class="bg-green-400 dark:bg-green-800 p-2 border-l-6 mt-2 inline">{{data.msg}}</h1>
    </div>
</template>
<script>
export default {
    name:"MsgSend",
    props:{
        data:String,
    }
}
</script>
<style >
    
</style>