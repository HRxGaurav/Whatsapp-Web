<template>
  <div class="grid grid-cols-12 h-screen">
    <div class="col-span-4">
      <div class="flex flex-col">

      <div class="bg-gray-200 dark:bg-gray-600 border-r-2" v-bind:style="{height: 65 + 'px'}">
        <HeaderLeft />
      </div>
      <div class=" items-center justify-center grid bg-gray-100 dark:bg-gray-800" v-bind:style="{height: 60 + 'px'}">
        <SearchLeft />
      </div>
      <div class="overflow-auto contactlist ">
          <div v-for="list in lists" :key="list.name" class="bg-gray-00 h-20 dark:bg-gray-600 border-r-2 ">
            <ContactList :name="list.name" :dp="list.dp" :msg="list.msg" />
          </div>
      </div>
      </div>
    </div>
    <div class="col-span-8">
      <div class="bg-gray-100 dark:bg-gray-600 " v-bind:style="{height: 65 + 'px'}">

      </div>
      <div class="chatbox">

      </div>
      <div class="bg-gray-100 dark:bg-gray-600 " v-bind:style="{height: 65 + 'px'}">

      </div>
    </div>
  </div>
</template>

<script>
import HeaderLeft from "./HeaderLeft.vue";
import SearchLeft from "./SearchLeft.vue";
import ContactList from "./ContactList.vue";
export default {
  components: { HeaderLeft, SearchLeft,ContactList },
  name: "MainComponent",
  props: {
    msg: String,
  },
  data() {
    return {
      lists: [
        {
          name: "abc",
          dp: "https://source.unsplash.com/1600x900/?beach",
          msg: [
            "https://source.unsplash.com/1600x900/?beach",
            "https://source.unsplash.com/1600x900/?beach",
            "https://source.unsplash.com/1600x900/?beach",
          ],
        },
        {
          name: "def",
          dp: "https://source.unsplash.com/1600x900/?beach",
          msg: [
            "https://source.unsplash.com/1600x900/?beach",
            "https://source.unsplash.com/1600x900/?beach",
            "https://source.unsplash.com/1600x900/?beach",
          ],
        },
        {
          name: "ghi",
          dp: "https://source.unsplash.com/1600x900/?beach",
          msg: [
            "https://source.unsplash.com/1600x900/?beach",
            "https://source.unsplash.com/1600x900/?beach",
            "https://source.unsplash.com/1600x900/?beach",
          ],
        },
        {
          name: "mno",
          dp: "https://source.unsplash.com/1600x900/?beach",
          msg: [
            "https://source.unsplash.com/1600x900/?beach",
            "https://source.unsplash.com/1600x900/?beach",
            "https://source.unsplash.com/1600x900/?beach",
          ],
        },
        {
          name: "jkl",
          dp: "https://source.unsplash.com/1600x900/?beach",
          msg: [
            "https://source.unsplash.com/1600x900/?beach",
            "https://source.unsplash.com/1600x900/?beach",
            "https://source.unsplash.com/1600x900/?beach",
          ],
        },
         {
          name: "pqr",
          dp: "https://source.unsplash.com/1600x900/?beach",
          msg: [
            "https://source.unsplash.com/1600x900/?beach",
            "https://source.unsplash.com/1600x900/?beach",
            "https://source.unsplash.com/1600x900/?beach",
          ],
        },
         {
          name: "stu",
          dp: "https://source.unsplash.com/1600x900/?beach",
          msg: [
            "https://source.unsplash.com/1600x900/?beach",
            "https://source.unsplash.com/1600x900/?beach",
            "https://source.unsplash.com/1600x900/?beach",
          ],
        },
         {
          name: "vwx",
          dp: "https://source.unsplash.com/1600x900/?beach",
          msg: [
            "https://source.unsplash.com/1600x900/?beach",
            "https://source.unsplash.com/1600x900/?beach",
            "https://source.unsplash.com/1600x900/?beach",
          ],
        },
         {
          name: "yz",
          dp: "https://source.unsplash.com/1600x900/?beach",
          msg: [
            "https://source.unsplash.com/1600x900/?beach",
            "https://source.unsplash.com/1600x900/?beach",
            "https://source.unsplash.com/1600x900/?beach",
          ],
        },
      ],
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.chatbox{
  height: calc(100vh - 130px);
}
.contactlist{
  height: calc(100vh - 125px);
}
</style>
