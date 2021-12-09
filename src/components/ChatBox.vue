<template >
  <div class="mb-5">
    <div class="text-grey-400 dark:text-white">
      <h1 v-for="chat in msg" :key="chat" class="">
        <div v-if="chat.issend">
          <MsgSend :data="chat" />
        </div>
        <div v-else>
          <MsgReceived :data="chat"/>
        </div>
      </h1>
    </div>
  </div>
</template>
<script>
import MsgSend from "./MsgSend.vue";
import MsgReceived from "./MsgReceived.vue";
export default {
  components: { MsgSend, MsgReceived },
  name: "ChatBox",
  props: {
    msg: Object,
  },
};
</script>
<style >
</style>