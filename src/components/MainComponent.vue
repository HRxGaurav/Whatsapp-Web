<template>
  <div class="grid grid-cols-12">
    <div class="col-span-4">
      <div class="flex flex-col">
        <div class="bg-gray-200 dark:bg-gray-600 border-r-2 border-gray-300" v-bind:style="{ height: 65 + 'px' }">
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
            border-gray-300
          "
          v-bind:style="{ height: 60 + 'px' }"
        >
          <SearchLeft />
        </div>
        <div class="overflow-auto contactlist border-gray-300 border-r-2">
          <div v-for="list in lists" :key="list.index" class="bg-gray-00 dark:bg-gray-600 border-r-2" v-on:click="for_right_headr_and_chatbox(list.name,list.msg,list.dp,list.index)">
            <ContactList :name="list.name" :dp="list.dp" :msg="list.msg" />
          </div>
        </div>
      </div>
    </div>
    <div class="col-span-8">
      <div class="bg-gray-200 dark:bg-gray-600" v-bind:style="{ height: 65 + 'px' }">
        <div v-if="show_right_header_and_chatbox">
        <HeaderRight :name="name_for_right_header" :dp="dp_for_right_header"/>
        </div>
      </div>
      <div class=" overflow-auto chatbox bg-chatbox_bg_light dark:bg-chatbox_bg_dark">
         <div v-if="show_right_header_and_chatbox">
          <ChatBox :msg="msg_for_chatbox"/>
        </div>
      </div>
       
      <div class="bg-gray-200 dark:bg-gray-600" v-bind:style="{ height: 65 + 'px' }">
        <div v-if="show_right_header_and_chatbox">
          <TypeBox :sendData="getData_from_typebox " :index="index_of_contact_in_chat"/>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import HeaderLeft from "./HeaderLeft.vue";
import SearchLeft from "./SearchLeft.vue";
import ContactList from "./ContactList.vue";
import HeaderRight from "./HeaderRight.vue";
import ChatBox from "./ChatBox.vue";
import TypeBox from "./TypeBox.vue";
import Data from '../assets/Data.js';
export default {
  components: { HeaderLeft, SearchLeft, ContactList,HeaderRight,ChatBox,TypeBox },
  name: "MainComponent",
  props: {
    msg: String,
  },
  methods:{
      show(){
        alert(Data);
      },
      for_right_headr_and_chatbox(name,msg,dp,index){
        this.index_of_contact_in_chat=index;
        this.show_right_header_and_chatbox=true;
        this.name_for_right_header=name;
        this.msg_for_chatbox=msg;
        this.dp_for_right_header=dp;
      },
      getData_from_typebox(chat_msg){
       this.msg_for_chatbox.push(chat_msg);   
      }
  },
  data() {
    return {
      Data,
      index_of_contact_in_chat:null,
      show_right_header_and_chatbox:false,
      name_for_right_header:null,
      dp_for_right_header:null,
      msg_for_chatbox:[
        {
          issend:Boolean,type:Text,msg:String
        }
      ],
      lists: [
        {
          index:0,
          name: "abc",
          dp: "https://source.unsplash.com/1600x900/?beach",
          msg:[
            {
               issend:true,
               type:Text,
               msg:"hii" 
            },
            {
                issend:true,
                type:Text,
                msg:"i am gaurav" 
            },
            {
                issend:false,
                type:Text,
                msg:"hellow"
            },
            {
                issend:true,
                type:Text,
                msg:"how are you"
            },
            {
                issend:false,
                type:Text,
                msg:"I am fine. and you?"
            },
            {
                issend:true,
                type:Text,
                msg:"I also fine"
            }
        ]
        },
        {
          index:1,
          name: "def",
          dp: "https://source.unsplash.com/1600x900/?beach",
          msg:[
            {
               issend:true,
               type:Text,
               msg:"hii" 
            },
            {
                issend:true,
                type:Text,
                msg:"i am gaurav" 
            },
            {
                issend:false,
                type:Text,
                msg:"hellow"
            },
            {
                issend:true,
                type:Text,
                msg:"how are you"
            },
            {
                issend:false,
                type:Text,
                msg:"I am fine. and you?"
            },
            {
                issend:false,
                type:Text,
                msg:"I also fine"
            }
        ]
        },
        {
          index:2,
          name: "ghi",
          dp: "https://source.unsplash.com/1600x900/?beach",
          msg:[
            {
               issend:true,
               type:Text,
               msg:"hii" 
            },
            {
                issend:true,
                type:Text,
                msg:"i am gaurav" 
            },
            {
                issend:false,
                type:Text,
                msg:"hellow"
            },
            {
                issend:true,
                type:Text,
                msg:"how are you"
            },
            {
                issend:false,
                type:Text,
                msg:"I am fine. and you?"
            },
            {
                issend:false,
                type:Text,
                msg:"I also fine"
            }
        ]
        },
        {
          index:3,
          name: "mno",
          dp: "https://source.unsplash.com/1600x900/?beach",
          msg:[
            {
               issend:true,
               type:Text,
               msg:"hii" 
            },
            {
                issend:true,
                type:Text,
                msg:"i am gaurav" 
            },
            {
                issend:false,
                type:Text,
                msg:"hellow"
            },
            {
                issend:true,
                type:Text,
                msg:"how are you"
            },
            {
                issend:false,
                type:Text,
                msg:"I am fine. and you?"
            },
            {
                issend:false,
                type:Text,
                msg:"I also fine"
            }
        ]
        },
        {
          index:4,
          name: "jkl",
          dp: "https://source.unsplash.com/1600x900/?beach",
          msg:[
            {
               issend:true,
               type:Text,
               msg:"hii" 
            },
            {
                issend:true,
                type:Text,
                msg:"i am gaurav" 
            },
            {
                issend:false,
                type:Text,
                msg:"hellow"
            },
            {
                issend:true,
                type:Text,
                msg:"how are you"
            },
            {
                issend:false,
                type:Text,
                msg:"I am fine. and you?"
            },
            {
                issend:false,
                type:Text,
                msg:"I also fine"
            }
        ]
        },
        {
          index:5,
          name: "pqr",
          dp: "https://source.unsplash.com/1600x900/?beach",
          msg:[
            {
               issend:true,
               type:Text,
               msg:"hii" 
            },
            {
                issend:true,
                type:Text,
                msg:"i am gaurav" 
            },
            {
                issend:false,
                type:Text,
                msg:"hellow"
            },
            {
                issend:true,
                type:Text,
                msg:"how are you"
            },
            {
                issend:false,
                type:Text,
                msg:"I am fine. and you?"
            },
            {
                issend:false,
                type:Text,
                msg:"I also fine"
            }
        ]
        },
        {
          index:6,
          name: "stu",
          dp: "https://source.unsplash.com/1600x900/?beach",
          msg:[
            {
               issend:true,
               type:Text,
               msg:"hii" 
            },
            {
                issend:true,
                type:Text,
                msg:"i am gaurav" 
            },
            {
                issend:false,
                type:Text,
                msg:"hellow"
            },
            {
                issend:true,
                type:Text,
                msg:"how are you"
            },
            {
                issend:false,
                type:Text,
                msg:"I am fine. and you?"
            },
            {
                issend:false,
                type:Text,
                msg:"I also fine"
            }
        ]
        },
        {
          index:7,
          name: "vwx",
          dp: "https://source.unsplash.com/1600x900/?beach",
          msg:[
            {
               issend:true,
               type:Text,
               msg:"hii" 
            },
            {
                issend:true,
                type:Text,
                msg:"i am gaurav" 
            },
            {
                issend:false,
                type:Text,
                msg:"hellow"
            },
            {
                issend:true,
                type:Text,
                msg:"how are you"
            },
            {
                issend:false,
                type:Text,
                msg:"I am fine. and you?"
            },
            {
                issend:false,
                type:Text,
                msg:"I also fine"
            }
        ]
        },
        {
          index:8,
          name: "yz",
          dp: "https://source.unsplash.com/1600x900/?beach",
          msg:[
            {
               issend:true,
               type:Text,
               msg:"hii" 
            },
            {
                issend:true,
                type:Text,
                msg:"i am gaurav" 
            },
            {
                issend:false,
                type:Text,
                msg:"hellow"
            },
            {
                issend:true,
                type:Text,
                msg:"how are you"
            },
            {
                issend:false,
                type:Text,
                msg:"I am fine. and you?"
            },
            {
                issend:false,
                type:Text,
                msg:"I also fine"
            }
        ]
        },
      ],
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style >
.contactlist {
  height: calc(100vh - 125px);
}
.chatbox {
  height: calc(100vh - 130px);
}

</style>
