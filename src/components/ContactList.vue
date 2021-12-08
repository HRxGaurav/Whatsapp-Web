<template>
  <div class="grid grid-cols-12 text-grey-400 dark:text-white truncate">
    <div class="col-span-2">
      <img
        :src="dp"
        alt=""
        class="h-12 w-12 rounded-full ml-4 mt-5"
      />
    </div>
    <div class="col-span-10 border-b-2 ml-3">
      <div class="flex flex-col items-start">
        <h1 class="mt-3 mr-16">{{ name }}</h1>
        <h3 class="mb-3 truncate w-80">{{ msg[msg.length - 1] }}</h3>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "ContactList",
  props: {
    name: String,
    dp: String,
    msg: Array,
  },
};
</script>
<style>
</style>