<template>
  <div class="item" @resize="chang">
    <div v-if="currenUser">
      <img :src="currenUser.src" alt />
      <span>{{currenUser.name}}</span>
      <ul>
        <li v-for="item in (currenUser.currenhua)" :key="item">{{item}}</li>
      </ul>
    </div>
    <p v-else>请选择用户</p>
  </div>
</template>
<script>
export default {
  props: ["currenUser"],
  methods: {
    chang() {
      console.log(555);
    }
  }
};
</script>
<style scoped>
div.item {
  height: 80%;
  border: 1px solid red;
  overflow-y: scroll;
}
img {
  width: 40px;
  height: 40px;
  vertical-align: middle;
}
</style>