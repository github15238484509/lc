<template>
  <div class="flex">
    <div class="left">
      <conment :currenUser = currenUser></conment>
      <writecon></writecon>
    </div>
    <div class="right">
      <preson :userList="userList" @emitEvent="emitEvent"></preson>
    </div>
    
  </div>
</template>
<script>
import conment from "./components/conment.vue";
import preson from "./components/preson.vue";
import writecon from "./components/writecon.vue";
export default {
  data() {
    return {
      userList: [
        {name: "笑话",src:   require("./assets/0.jpg") },
        { name: "天才", src: require("./assets/1.jpg")  },
        { name: "傻瓜", src: require("./assets/2.jpg")  },
        { name: "孙悟空", src: require("./assets/3.jpg")  }
      ],
      currenUser:{name: "笑话",src:   require("./assets/0.jpg") }
    };
  },
  methods:{
    emitEvent(e){
      this.currenUser = this.userList[e]
    }
  },
  components: {
    conment,
    preson,
    writecon
  }
};
</script>
<style scoped>
.flex {
  width: 500px;
  height: 500px;
  border: 1px solid red;
  box-sizing: border-box;
  margin: 20px auto;
  display: flex;
}
.flex .left {
  width: 80%;
}
.flex .right {
  width: 20%;
}
</style>
