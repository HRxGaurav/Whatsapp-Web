<template >
    <div class="mt-3 flex justify-start ml-20">
        <h1 class="bg-white dark:bg-gray-600 p-2 border-l-6 mt-2 inline">{{data.msg}}</h1>
    </div>
</template>
<script>
export default {
    name:"MsgReceived",
    props:{
        data:String,
    }
}
</script>
<style >
    
</style>