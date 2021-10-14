<template>
  <div class="container">
        <div class="alert alert-light" style="width:75%;">
            <p>{{ message }}</p>

            <p><slot /></p>
            <div class="itembox">
            <p>{{favicon}}
              <button class="favbutton" v-on:click="FavCount">イイネ！</button>
              {{favcount}}
            </p> 
            </div>
        </div>
  </div>
</template>

<style>
  .alert {
    
  }
</style>

<script>
export default {
    name: 'Tweet',
    props: ['message',],
    

    data() {
       return {
         favicon: '★',
         favcount: 0,
       }
    },

    methods: {
        FavCount() {
      //イイネのクリック数をカウントして表示させるメソッド。
      this.favcount++
      console.log(this.favcount)
    }
    }
}
</script>