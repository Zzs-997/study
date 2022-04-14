<template>
  <div id="App">
    <div class="content">
      <charCom :currentUser="currentUser"></charCom>
      <userListCom @chooseuser="toggleUser" :userlist="userlist"></userListCom>
    </div>
  </div>
</template>

<script>
import charCom from "./components/chatCom.vue";
import userListCom from "./components/userListCom.vue";

export default {
  name: "App",
  components: {
    charCom,
    userListCom,
  },
  data() {
    return {
      userlist: [
        {
          username: "美女1",
          headerimg: require("./assets/img/1.webp"),
        },
        {
          username: "美女2",
          headerimg: require("./assets/img/2.jpg"),
        },
        {
          username: "美女3",
          headerimg: require("./assets/img/3.png"),
        },
        {
          username: "美女4",
          headerimg: require("./assets/img/4.jpeg"),
        },
      ],
      currentUser: {
        username: "美女1",
        headerimg: require("./assets/img/1.webp"),
      },
    };
  },
  methods: {
    toggleUser: function (index) {
      this.currentUser = this.userlist[index];
    },
  },
};
</script>

<style scoped>
.content {
  display: flex;
  width: 800px;
  height: 600px;
  margin: 50px auto;
}
</style>
