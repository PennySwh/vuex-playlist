<template>
  <div id="app">
    <product-list-one ></product-list-one>
    <product-list-two ></product-list-two>
  </div>
</template>

<script>
import ProductListOne from './components/ProductListOne.vue'
import ProductListTwo from './components/ProductListTwo.vue'
export default {
  name: 'app',
  components:{
    'product-list-one':ProductListOne,
    'product-list-two':ProductListTwo
  },
  data () {
    return {
      products:[
        {name:"马云",price:200},
        {name:"马化腾",price:140},
        {name:"马冬梅",price:100},
        {name:"马蓉",price:60}
      ]
    }
  }
}
</script>

<style>
body{
  font-family: Ubuntu;
  color: #555;
}
</style>
