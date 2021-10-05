<template>
  <div class="container">
    <div class="alert alert-info">
        <div class="alert alert-light mx-4" style="width:25rem">
            <p>{{ message }}</p>
        </div>
    </div>
  </div>
</template>

<script>
export default {
    name: 'Tweet',
    props: ['message'],

    data() {
       
    },

    methods: {

    }
}
</script>