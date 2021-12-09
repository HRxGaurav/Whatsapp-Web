<template >
  <div class=" flex items-center justify-start text-grey-400 dark:text-white">
    <div class="text-left mt-4 mr-5 ml-5">
      <button class="mr-3">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          class="h-8 w-8"
          fill="none"
          viewBox="0 0 24 24"
          stroke="currentColor"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
            d="M14.828 14.828a4 4 0 01-5.656 0M9 10h.01M15 10h.01M21 12a9 9 0 11-18 0 9 9 0 0118 0z"
          />
        </svg>
      </button>
      <button>
        <svg
          xmlns="http://www.w3.org/2000/svg"
          class="h-8 w-8"
          fill="none"
          viewBox="0 0 24 24"
          stroke="currentColor"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
            d="M15.172 7l-6.586 6.586a2 2 0 102.828 2.828l6.414-6.586a4 4 0 00-5.656-5.656l-6.415 6.585a6 6 0 108.486 8.486L20.5 13"
          />
        </svg>
      </button>
    </div>
    <div class="flex rounded-full bg-white dark:bg-grey-600 mt-2">
      <input
        type="text"
        class="px-5 py-2 rounded-full dark:bg-gray-500 text-gray-600 dark:text-white"
        placeholder="Type a message"
        v-model="inputmsg.msg"
        v-bind:style="{ width: 53 + 'vw' }"
      />
    </div>
    <div v-if="inputmsg.msg">
      <button type="submit" v-on:click="getmsg()" class="mt-3 ml-4">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          class="h-8 w-8"
          fill="none"
          viewBox="0 0 24 24"
          stroke="currentColor"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
            d="M13 5l7 7-7 7M5 5l7 7-7 7"
          />
        </svg>
      </button>
    </div>
    <div v-else>
      <button type="submit" v-on:click="getmsg()" class="mt-3 ml-4">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          class="h-8 w-8"
          fill="none"
          viewBox="0 0 24 24"
          stroke="currentColor"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
            d="M19 11a7 7 0 01-7 7m0 0a7 7 0 01-7-7m7 7v4m0 0H8m4 0h4m-4-8a3 3 0 01-3-3V5a3 3 0 116 0v6a3 3 0 01-3 3z"
          />
        </svg>
      </button>
    </div>
  </div>
</template>
<script>
export default {
  name: "TypeBox",
  props: {
    sendData: Function,
  },
  data() {
    return {
      inputmsg: [
        {
          issend:false,
          type:Text,
          msg:null
        }
      ],
      sendmsg: [
        {
          issend:false,
          type:Text,
          msg:null
        }
      ],
    };
  },
  methods: {
    getmsg() {
      this.sendmsg.msg = this.inputmsg.msg;
      this.inputmsg.msg = null;
      this.sendmsg.issend=true;
      this.sendmsg.type=Text;
      this.sendData(this.sendmsg);
    },
  },
};
</script>
<style >
</style>
