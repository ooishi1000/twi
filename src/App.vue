<template>
  <div id="app">
    <Form  v-on:event="EditTweet"/>
    <hr />
    <Tweet v-bind="tips">
      <div v-for="(rog, index) in rogs" :key="index">
          <h5 class="card" style="text-align:left">{{rog.name}} :<p style="color:black">{{rog.talk}}</p> </h5>
      </div>
    </Tweet>
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
     tips: {
       message: 'ツイート内容',
      //  moment: ,
     },
     rogs: [
        {name:'NAME', talk:'データ'},
        {name:'NAME', talk:'データ'},
        ],
     count: 0,
   } 
  },
  methods: {
    EditTweet(text) {
      this.count++
      console.log(this.count)
      console.log(text)
      // this.tweet = text
      this.rogs.unshift({name:'NAME', talk:text})
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
