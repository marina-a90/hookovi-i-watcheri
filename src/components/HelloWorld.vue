<template>
  <div class="hello">
    <h1 @click="h1Click">{{ msg }} {{ elephant }}</h1>
    <p>{{ parentData }}</p>
    <button @click="handleClick">Click me</button>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: {
      type: String,
      required: false,
      default: () => []
    },
    elephant: String,
    parentData: String
  },
  methods: {
    handleClick() {
      console.log("child clicked");
      this.$emit("button-clicked");
    },

    h1Click() {
      const lName = "A.";
      this.$emit("h1-clicked", lName);
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
