<template>
  <div id="app">
    <Form  v-on:event="EditTweet"/>

    <hr />
    <div class="container">
      <div class="alert alert-info" style="padding-left:10%;">
        <p>{{ message }}</p>
          <div v-for="(log, index) in logs" :key="index">
            <Tweet>
            <h5 class="card" style="text-align:left">{{log.name}} :
              <p class="msg">{{log.talk}}({{log.num}})</p> 
            </h5>
            <!-- 検索用のタグ？を付与。タブ切り替え機能でイイネしたツイートを表示（データベース系の検索機能）、イイネ数、日付順（ツイートした日付を取得、付与）、イイネした日時（イイネした日時を取得、付与）でソート可能にしたい。 -->
            </Tweet>
          </div>
      </div>
    </div>
  </div>
</template>

<style>

.card {
  background-color: rgb(255, 241, 223);
  margin: 10px auto 0px;
}
p .msg {
  font-size:12pt;
  color:black;
}
.itembox {
  margin-top: -20px;
  margin-bottom: 10px;
  height: 25px;
  text-align:right;
  background-color:rgb(255, 241, 223);
  border: 1px solid rgb(225, 225, 225);
}
.favbutton {
  font-size: 11px;
  width: 60px;
  height: 20px;
  border-radius: 17px;
  background-color: rgb(255, 223, 231);
}
.favbutton:hover {
    background-color: rgb(255, 202, 216);
  }
.favbutton:active {
  transform: translateY(2px);
}

</style>

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
    message:'ツイート内容',
     logs: [
       //メモ：ユーザー情報（ID。ネーム）をオブジェクトとして作成。最終的に表示。
       //メモ：ツイート内情報をオブジェクトとして作成。連想配列のツリー構造。
        {name:'NAME', talk:'データ',num:0},
        // {name:'NAME', talk:'データ',num:0},
        ],
     count: 0,
   } 
  },
  methods: {
    EditTweet(box) {
      //フォームから入力された名前とツイートを受け取り、データの中にあるオブジェクトに格納するメソッド。
      this.count++
      console.log(this.count)
      //メモ：push(最後尾追加),pop(最後尾取り出し)
      //メモ：unshift(先頭追加),shift(先頭取り出し)
      this.logs.unshift({name:box.named, talk:box.text, num:box.id})
      //メモ：ツイート表示数の上限。
      
    },
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
