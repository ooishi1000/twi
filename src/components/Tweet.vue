<template>
  <div class="container">
    <div class="alert alert-info">
        <div class="alert alert-light mx-4" style="width:25rem">
            <p>{{ message }}</p>

            <p><slot /></p>

            <!-- <p>{{ moment }}</p> -->
            
            <!-- <div v-for="(rog, index) in rogs" :key="index">
                <h5 class="card" style="text-align:left">{{rog.name}} :<p style="color:black">{{rog.talk}}</p> </h5>
            </div> -->
        </div>
    </div>
  </div>
</template>

<script>
export default {
    name: 'Tweet',
    props: ['message','moment'],
    

    data() {
       return {
        // rogs: [
        // {name:'NAME', talk:'データ'},
        // {name:'NAME', talk:'データ'},
        // ],
       }
    },

    methods: {
        // plusTweet(text) {
        //    this.$set(this.rogs,'NAME',text)
        // }
    }
}
</script>