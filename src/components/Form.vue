<template>
  <div class="container">
    <div class="alert alert-info">
      <h2>title</h2>
      <p>{{ test }}</p>

      <input type="text" name="tweetname" placeholder="名前" v-model="tweetname">
      <br>

      <textarea name="tweet" id="" cols="30" rows="3" placeholder="今なにしてる？" v-model="textarea"></textarea>
      <br>
      <input class="button" type="submit" value="ツイート" v-on:click="doTweet" />
    </div>
  </div>
</template>

<style>
  .container {
    width: 700px;
  }
  .button {
    border-radius: 10px;
    box-shadow: 3px 3px 3px gray;
  }
  .button:hover {
    background-color: rgb(182, 211, 211);
  }
</style>

<script>
export default {
  data() {
    return {
      test: 'test',
      textarea: '',
      tweetname:'',
      tweetcount:0,

    }
  },

    methods: {
        doTweet() {
          let numb = this.tweetcount += 1
          let box = {text:this.textarea, named:this.tweetname, id:numb}
          this.test = box.text
          this.$emit("event", box)
          this.textarea = ''
          //localStorage.setItemメソッドでストレージにtweetcountとboxの中身を入れたいけどJSONっていう変換技術が要るっぽい。ここでストレージに入れた値をAppのほうでgetで取り出す。取り出すときたぶんmounted()使うっぽい。要検証。
          //storageの話はJSの本の456p～。
          //イイネ数も格納しないといけない。
        }
    }
}


</script>

