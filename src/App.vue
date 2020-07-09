<template>
  <div id="app">    
    <input v-model="text" class="item-text" />
    <button @click="addItem">Добавить</button>
    <the-list ref="list" />
  </div>
</template>

<script>
import TheList from "./components/TheList.vue";

export default {
  name: "App",
  components: {
    TheList
  },
  data: function() {
    return {
      text: ""
    };
  },
  methods : {
    addItem() {
      this.$refs.list.addItem(this.text);
      this.text = "";
    }
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: left;
  color: #32CD32;
  margin-top: 20px;
}
button {
  background-color: #FF0000;
  color: black;
  padding: 10px;
  border-radius: 15px;
  height: 4rem;
  font-size: 2rem;
  margin-left: 20px;
}
.item-text {
 height: 2rem;
 font-size: 1.5rem;
}
</style>
