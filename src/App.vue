<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld :msg="firstName" 
    @button-clicked="handleButtonClicked"
    @h1-clicked="handleh1clicked"
    elephant="slon"
    parentData="parent data"/>
    
    <input type="text" v-model="firstName"/>
    <input type="text" v-model="lastName"/>
    <input type="number" v-model="age"/>
    {{ fullName }}
    {{ randNum }}
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";

export default {
  name: "app",
  components: {
    HelloWorld
  },

  data() {
    return {
      firstName: "Marina",
      lastName: "",
      age: 1
    };
  },

  computed: {
    fullName() {
      return `${this.firstName} ${this.lastName} - ${this.age}`;
    },

    randNum() {
      return this.age * Math.random();
    }
  },

  watch: {
    firstName(newValue, oldValue) {
      console.log(newValue);
      if (newValue === "Marina") {
        alert("Hi");
      }
    }
  },

  methods: {
    handleButtonClicked() {
      console.log("parent clicked");
    },
    handleh1clicked(event) {
      console.log("h1 clicked");
      this.firstName = event;
    }
  },

  beforeCreate() {
    console.log("before create");
  },

  created() {
    console.log("created");
  },

  beforeMount() {
    console.log("before mount");
  },

  mounted() {
    console.log("mounted");
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
