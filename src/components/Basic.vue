<template>
  <div class="basic">
    <h1>{{ msg }}</h1>
    <h2>Data Binding</h2>
    <div> <span>{{ oneWay }}</span></div>
    <h2>Ecosystem</h2>
    
  </div>
</template>

<script>
export default {
  name: 'basic',
  data () {
    return {
      msg: 'The demo of vue directive',
      oneWay: 'This is one way binding',
      twoWay: 'This is tow way binding'
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
