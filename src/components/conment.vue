<template>
  <div>
      <img :src="currenUser.src" alt="">
      <span>{{currenUser.name}}</span>
  </div>
</template>
<script>
export default {
  props: ["currenUser"]
};
</script>
<style scoped>
img{
    width: 40px;
    height: 40px;
    vertical-align: middle;
}
</style>