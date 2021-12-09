<template>
  <div>
    <div class="h-14 items-center justify-center grid bg-gray-100 dark:bg-gray-800">
      <h1 v-for="list in datas" :key="list.name">{{ list.name }} {{ list.dp }}</h1>
      
    </div>
  </div>
</template>
<script>
import datas from "./assets/Data.js"
console.log(datas);
export default {
  name: "Test",
  data(){
    return {
        datas,
    }
  }
};
</script>
<style >
</style>