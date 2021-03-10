<template>
  <div>
    <input type="text" v-model="content" @keydown.enter="sendEvent" />
    <button @click="sendEvent">发送</button>
  </div>
</template>
<script>
export default {
  props: ["currenUser"],
  data() {
    return {
      content: ""
    };
  },
  methods: {
    sendEvent() {
      if (!this.currenUser) {
        alert("请选择用户");
        return;
      }
      if (!this.content) {
        alert("请输入内容");
        return;
      }
      this.$emit("sendWrite", this.content);
      this.content = "";
    }
  }
};
</script>
<style scoped>
</style>