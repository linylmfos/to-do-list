<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <h1>{{ msgfromfather }}</h1>
    <!-- <button v-on:click="onClickMe">Click!</button> -->
    <button v-on:click="onClickMe">start to say!</button>
  </div>
</template>

<script>
export default {
  data: function(){
    return {
      msg: 'hello from component a!'
    }
  },
  props: ['msgfromfather'],
  events: {
    'onAddnew': function (items){
      console.log(items)
    }
  },
  methods: {
    onClickMe: function (){
    //  console.log(this.msgfromfather)
     this.$emit('child-tell-me-something', this.msg );
      this.$dispatch('child-tell-me-something', this.msg )
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
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
