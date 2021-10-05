<template>
  <div class="container">
    <div class="alert alert-info">
      <h2>title</h2>
      <p>{{ test }}</p>
      <textarea name="tweet" id="" cols="30" rows="3" placeholder="今なにしてる？" v-model="textarea"></textarea>
      <br>
      <input type="submit" value="ツイート" v-on:click="doTweet" />
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      test: 'test',
      textarea: ''
    }
  },

    methods: {
        doTweet() {
          let text = this.textarea
          this.test = text
          this.$emit("event", text)
          this.textarea = ''
        }
    }
}


</script>

