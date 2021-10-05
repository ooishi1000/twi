<template>
  <div id="app">
    <Form  v-on:event="EditTweet"/>
    <hr />
    <Tweet v-bind:message="tweet"/>
  </div>
</template>

<script>
import Form from "./components/Form.vue";
import Tweet from "./components/Tweet.vue";

export default {
  name: "app",
  components: {
    Form,
    Tweet,
  },
  data() {
   return {
     tweet: 'ツイート内容',
     count: 0
   } 
  },
  methods: {
    EditTweet(text) {
      this.count++
      this.tweet = text
    }
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
