<template>
  <div class="grid grid-cols-12">
    <div class="col-span-4">
      <div class="flex flex-col">
        <div class="bg-gray-200 dark:bg-gray-600 border-r-2" v-bind:style="{ height: 65 + 'px' }">
          <HeaderLeft />
        </div>
        <div
          class="
            items-center
            justify-center
            grid
            bg-gray-100
            dark:bg-gray-800
            border-r-2
          "
          v-bind:style="{ height: 60 + 'px' }"
        >
          <SearchLeft />
        </div>
        <div class="overflow-auto contactlist">
          <div v-for="list in lists" :key="list.name" class="bg-gray-00 dark:bg-gray-600 border-r-2" v-on:click="for_right_headr_and_chatbox(list.name,list.msg,list.dp)">
            <ContactList :name="list.name" :dp="list.dp" :msg="list.msg" />
          </div>
        </div>
      </div>
    </div>
    <div class="col-span-8">
      <div class="bg-gray-100 dark:bg-gray-600" v-bind:style="{ height: 65 + 'px' }">
        <div v-if="show_right_header_and_chatbox">
        <HeaderRight :name="name_for_right_header" :dp="dp_for_right_header"/>
        </div>
      </div>
      <div class="chatbox">
         <div v-if="show_right_header_and_chatbox">
          <ChatBox :msg="msg_for_chatbox"/>
        </div>
      </div>
       
      <div
        class="bg-gray-100 dark:bg-gray-600"
        v-bind:style="{ height: 65 + 'px' }"
      ></div>
    </div>
  </div>
</template>

<script>
import HeaderLeft from "./HeaderLeft.vue";
import SearchLeft from "./SearchLeft.vue";
import ContactList from "./ContactList.vue";
import HeaderRight from "./HeaderRight.vue";
import ChatBox from "./ChatBox.vue";
export default {
  components: { HeaderLeft, SearchLeft, ContactList,HeaderRight,ChatBox },
  name: "MainComponent",
  props: {
    msg: String,
  },
  methods:{
      for_right_headr_and_chatbox(name,msg,dp){
        this.show_right_header_and_chatbox=true;
        this.name_for_right_header=name;
        this.msg_for_chatbox=msg;
        this.dp_for_right_header=dp;
      }
  },
  data() {
    return {
      show_right_header_and_chatbox:false,
      name_for_right_header:null,
      dp_for_right_header:null,
      msg_for_chatbox:[],
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
        {
          name: "parth",
          dp: "https://source.unsplash.com/1600x900/?beach",
          msg: [
            "https://source.unsplash.com/1600x900/?beach",
            "https://source.unsplash.com/1600x900/?beach",
            "https://source.unsplash.com/1600x900/?beach",
          ],
        },
        {
          name: "gaurav",
          dp: "https://source.unsplash.com/1600x900/?beach",
          msg: [
            "https://source.unsplash.com/1600x900/?beach",
            "https://source.unsplash.com/1600x900/?beach",
            "https://source.unsplash.com/1600x900/?beach",
          ],
        },
        {
          name: "aadi",
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
.contactlist {
  height: calc(100vh - 125px);
}
.chatbox {
  height: calc(100vh - 130px);
}
</style>
