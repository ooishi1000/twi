<template>
  <div class="container">
    <div class="alert alert-info" style="padding-left:16%;">
        <div class="alert alert-light" style="width:85%;">
            <p>{{ message }}</p>

            <p><slot /></p>
            <p>{{favicon}}</p>

            <!-- カウントできるfavボタンをつける -->

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
         favicon: '★'
       }
    },

    methods: {
        
    }
}
</script>