<template>
  <ul >
    <li v-for="(item,index) in userList" :key="item" @click="emitEvent(index,$event)">
      <img :src="item.src" alt />
      <span>{{item.name}}{{index}}</span>
    </li>
  </ul>
</template>
<script>
export default {
  props: ["userList"],
  methods: {
    emitEvent(e, event) {
      this.$emit("emitEvent", e);
    }
  }
};
</script>
<style scoped>
ul,
li {
  list-style: none;
  margin: 0;
  padding: 0;
}
ul {
  width: 100%;
  height: 100%;
}
ul li {
  height: 30px;
  line-height: 30px;
  border: 1px dotted black;
}
ul li img {
  height: 100%;
  vertical-align: middle;
}
</style>